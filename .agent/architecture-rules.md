# Agent Instructions: MedSIS Architecture & Routing

## Core Directives for Expo Router
1. **Never build monolithic screens.** The files located in `app/(tabs)/` or `app/auth/` must remain under 150 lines of code. They are strict compositional wrappers. Shared layout elements like custom headers, skeletons, and hooks should be extracted (e.g., `components/TabsHeader.tsx`, `components/ui/Skeleton.tsx`, `hooks/useNavigationMode.ts`).
2. **Feature-based separation.** When asked to build a new feature, automatically create a new subdirectory in `components/` (e.g., `components/enrollment/`) and assemble your UI blocks there. Include those blocks in the `app/` router.
3. **State Management.** The application relies on a custom Redux-like store architecture implemented on top of React Context APIs located in the `redux/` folder. Use the custom hooks `useSelector` and `useDispatch` from `@/redux/store` to connect layout pages and components to state.

## Component File Structure
Every component generated must:
- Use Named Exports (e.g., `export const Header = () => {}`) 
- Avoid default exports unless it is necessary for Expo Router pages.
- Group sub-components together logically.
