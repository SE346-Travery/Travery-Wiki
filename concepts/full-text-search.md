# Concept: Full-text Search

Travery implements advanced search capabilities for its core entities (primarily [[Tour]] and [[TourInstance]]) using **Hibernate Search** with a **Lucene** backend.

## Architecture
- **In-process Indexing**: Changes to database entities are automatically synchronized with the Lucene index via Spring Data JPA event listeners.
- **Lucene Backend**: Uses local file-system based indexes (configured in `application.yml`).

## Search Logic Implementation
The search logic is encapsulated in `TourSearchCustomRepositoryImpl`, utilizing the Hibernate Search DSL.

### Key Features
1. **Keyword Matching**:
    - Targets `name`, `description`, and `destination.name` fields.
    - **Boosting**: The `name` field has a **2.0f boost**, ensuring tours with matching titles appear higher in results than those with matches only in the description.
    - **Fuzzy Search**: Implements `fuzzy(1)` to provide tolerance for single-character typos.
2. **Filtering**:
    - **Range Predicates**: Used for filtering by `pricePerAdult` (min/max) and `averageRating`.
    - **Match Predicates**: Used for exact matching on `destination.id` and `isCustom`.
3. **Availability (Nested Predicates)**:
    - Performs nested searches on the `tourInstances` list.
    - Filters for instances with a specific `startDate` and a status of `OPEN`.
4. **Sorting**:
    - Supports sorting by `pricePerAdult`, `averageRating`, `name`, and `id`.
    - **Relevance Score**: Default sort order is based on Lucene's relevance score (`f.score()`) when a keyword is provided.

## Configuration
Indexing is enabled via the `@Indexed` annotation on entity classes. Fields are marked with `@FullTextField` (for analyzed text) or `@GenericField` (for exact/range/sortable values).

```java
@Indexed
public class Tour extends AbstractBaseEntity {
  @FullTextField(analyzer = "standard")
  private String name;

  @GenericField(sortable = Sortable.YES)
  private Double averageRating;
  
  @IndexedEmbedded
  private Destination destination;
}
```

## References
- [[travery-backend]]
- [[Tour]]
