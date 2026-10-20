---
name: clean-react-component
description: Guides the creation of accessible, modular React components with TypeScript and clean state.
---

# Clean React Component

## Overview
Use this skill when scaffolding or refactoring a React UI component. It ensures that the component follows single-responsibility principles, handles loading and error states cleanly, and includes accessible semantic HTML.

## Workflow
1. **Analyze Component Requirements**:
   - Identify props, state variables, and callbacks needed.
   - Separate presentational logic from data fetching or side effects.
2. **Define TypeScript Interfaces**:
   - Export an explicit `Props` interface documenting every parameter.
3. **Implement Component Markup**:
   - Use semantic HTML tags (`<button>`, `<article>`, `<nav>`).
   - Add accessible ARIA attributes where semantic HTML is insufficient.
4. **Handle Edge States**:
   - Provide explicit fallback rendering for loading, empty, and error states.
5. **Add Default / Named Exports**:
   - Export both the component as a named export and sub-types as needed.

## Constraints
- Never use inline styles; rely on CSS classes or utility tokens.
- Do not mutate props directly.
- Avoid nesting hooks inside conditional statements or loops.
- Do not use `any` in TypeScript type definitions.

## Examples

### Input Request
> "Create a UserCard component displaying a user's avatar, name, email, and an onFollow callback."

### Target Output Structure
```tsx
import React from 'react';

export interface UserCardProps {
  id: string;
  name: string;
  email: string;
  avatarUrl?: string;
  isFollowing?: boolean;
  onFollow?: (id: string) => void;
}

export const UserCard: React.FC<UserCardProps> = ({
  id,
  name,
  email,
  avatarUrl,
  isFollowing = false,
  onFollow,
}) => {
  return (
    <article className="user-card" aria-label={`Profile card for ${name}`}>
      <img
        src={avatarUrl || '/default-avatar.png'}
        alt={`${name}'s avatar`}
        className="user-card__avatar"
      />
      <div className="user-card__info">
        <h3 className="user-card__name">{name}</h3>
        <p className="user-card__email">{email}</p>
      </div>
      {onFollow && (
        <button
          type="button"
          onClick={() => onFollow(id)}
          className={`user-card__btn ${isFollowing ? 'following' : ''}`}
        >
          {isFollowing ? 'Unfollow' : 'Follow'}
        </button>
      )}
    </article>
  );
};
```

## Completion Criteria
- [ ] Props interface is strictly typed without `any`.
- [ ] Semantic HTML and accessibility labels are applied.
- [ ] Optional props provide safe defaults.
- [ ] No inline styling is used.
