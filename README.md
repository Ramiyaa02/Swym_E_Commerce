# 🛒 Wishlist Storefront

A modern **React + TypeScript e-commerce storefront** featuring robust wishlist management with an emphasis on **atomic wishlist merging**, duplicate prevention, and client-side persistence.

This project was developed as part of the **Swym CX AI-Proficiency Build Round**, where the focus was on requirement clarification, engineering judgment, AI-assisted development, and iterative problem solving.

---

## 🌐 Live Demo

🔗 https://app-d0whjvqev7y9.appmedo.com

---

## 📖 Problem Statement

Build a simple e-commerce storefront with a wishlist feature.

The primary engineering requirement was to support **merging two independent wishlists into one** while correctly handling duplicate products and preserving data consistency.

The project intentionally received an ambiguous specification, requiring requirement clarification, architectural decisions, and engineering trade-offs before implementation.

---

# ✨ Features

- Browse products
- Product search
- Category filtering
- Create multiple wishlists
- Rename wishlist
- Delete wishlist
- Add products to wishlists
- Remove products from wishlists
- Merge two wishlists
- Automatic duplicate detection
- LocalStorage persistence
- Responsive UI
- Accessible components
- Toast notifications

---

# 🏗️ Tech Stack

- React 18
- TypeScript
- Vite
- Tailwind CSS
- shadcn/ui
- React Router
- React Context API
- LocalStorage
- Lucide React
- Sonner Toast

---

# 🏛️ Architecture

```
React
│
├── Components
├── Context API
├── Custom Hooks
├── Utilities
├── Static Product Data
└── LocalStorage
```

The application follows a component-based architecture with clear separation between presentation, business logic, and persistence.

---

# 📦 Data Model

### Product

- id
- name
- description
- category
- price
- image

### Wishlist

- id
- name
- created_at
- updated_at

### Wishlist Item

- id
- wishlist_id
- product_id
- added_at

---

# 🔀 Wishlist Merge Strategy

The merge operation follows a **set-union** approach.

Steps:

1. Validate source and target wishlist.
2. Prevent merging the same wishlist.
3. Detect duplicate products using `product_id`.
4. Copy only unique products.
5. Delete the source wishlist.
6. Update target metadata.
7. Persist changes atomically.

Time Complexity:

```
O(Source Items + Target Items)
```

---

# 📌 Engineering Decisions

Since the assessment intentionally left several requirements undefined, the following assumptions were made:

- Single-user application
- Frontend-only architecture
- LocalStorage persistence
- Static product catalog
- Merge removes duplicate products
- Products identified by unique IDs
- One product appears only once per wishlist

These decisions were documented before implementation and refined during development.

---

# ⚖️ Tradeoffs

### LocalStorage

Pros

- Simple
- No backend required
- Fast implementation

Cons

- Browser-specific
- No cross-device synchronization
- Limited storage

---

### React Context

Chosen over Redux because the application state is relatively small and localized.

---

# 🧪 Testing

The application was manually verified against multiple scenarios.

Test coverage includes:

- Empty wishlist
- Empty merge target
- Merge same wishlist
- Duplicate products
- Browser refresh
- Corrupted LocalStorage
- Missing product IDs
- Long wishlist names
- Large wishlists
- Invalid user actions
- Mobile responsiveness
- Accessibility

---

# 📂 Project Structure

```
src/
├── components/
├── contexts/
├── hooks/
├── pages/
├── lib/
├── data/
├── types/
└── App.tsx
```

---

# 🤖 AI-Assisted Development

This project was developed using AI as an engineering assistant rather than a code generator.

The workflow followed:

1. Requirement clarification
2. Assumption documentation
3. Architecture planning
4. Iterative implementation
5. QA review
6. Edge-case verification
7. Documentation refinement

The implementation emphasizes engineering judgment, verification, and iterative refinement over one-shot code generation.

---

# 📄 Documentation

The repository also includes:

- V1 Specification
- Project Documentation
- AI Development Log
- Requirements Document

---

# 🚀 Future Improvements

- User authentication
- Backend persistence
- Cloud synchronization
- Wishlist sharing
- Import / Export wishlists
- Automated testing
- Product recommendations
- AI-powered product discovery

---

# 👩‍💻 Author

**Ramiyaa Sundar**

B.Tech Computer Science Engineering  
SASTRA Deemed University

Built for the **Swym CX AI-Proficiency Build Round**.
