# Equipment Borrowing Management System - Design Guidelines

## Design Approach
**System-Based Approach**: Material Design principles adapted for productivity and data management. This is a utility-focused application prioritizing efficiency, clarity, and learnability over visual flair.

## Layout Architecture

**Spacing System**
- Use Tailwind units: 2, 4, 6, 8, 12, 16, 20
- Card padding: p-6 to p-8
- Section spacing: mb-8 to mb-12
- Form field gaps: gap-4 to gap-6
- Container max-width: max-w-7xl

**Grid Strategy**
- Desktop: Two-column layout (1/3 form + 2/3 table) using grid-cols-3
- Tablet: Stack to single column
- Mobile: Full-width stacked layout

## Typography Hierarchy

**Font Stack**: Inter or Roboto from Google Fonts
- Page Title (H1): text-3xl, font-bold
- Section Headers (H2): text-xl, font-semibold  
- Table Headers: text-sm, font-medium, uppercase tracking-wide
- Body Text: text-base
- Helper Text/Notes: text-sm
- Form Labels: text-sm, font-medium

## Component Library

### Navigation Header
- Sticky top bar with app title and icon
- Height: h-16
- Vietnamese title: "Quản lý mượn thiết bị" with equipment emoji
- No complex navigation needed

### Request Form Card
- Elevated card with subtle shadow
- Width: Full width on mobile, 1/3 on desktop
- Form fields stack vertically with gap-4
- Labels above inputs
- Full-width inputs with h-10
- Primary CTA button at bottom, full-width
- Clear visual hierarchy: Label → Input → Button

### Management Table Card
- Elevated card matching form style
- Width: Full width on mobile, 2/3 on desktop
- Responsive table with horizontal scroll on mobile
- Column headers with sorting indicators
- Row hover states for better scanning
- Action buttons inline per row (icon buttons or small buttons)
- Status badges with distinct visual treatment
- Footer note in smaller text below table

### Form Inputs
- Standard height: h-10
- Border radius: rounded-md
- Text inputs: Full width with clear focus states
- Select dropdown: Chevron icon, consistent height
- Date picker: Calendar icon, native input enhanced
- Consistent spacing: mb-4 between fields

### Buttons
**Primary Button** (Submit Request)
- Height: h-10, rounded-md
- Full-width in form context
- Font: font-medium

**Action Buttons** (Approve/Reject)
- Smaller size: h-8, px-4
- Rounded: rounded-md
- Inline display in table cells
- Gap between buttons: gap-2

### Status Indicators
- Badge style: rounded-full, px-3, py-1, text-xs, font-semibold
- Three states: Pending (Chờ duyệt), Approved (Đã duyệt ✅), Rejected (Từ chối ❌)
- Use emojis for quick visual scanning

### Table Design
- Striped rows for easier scanning (even rows with subtle background)
- Compact padding: px-4, py-3
- Borders: Border-collapse with 1px borders
- Header row: Sticky on scroll, distinct visual weight
- Text alignment: Left for text, center for actions
- Mobile: Stack or horizontal scroll with min-width preserved

## Page Structure

**Single Dashboard View**
1. Header bar (h-16)
2. Main container (max-w-7xl, mx-auto, p-6)
3. Grid layout (grid-cols-1 lg:grid-cols-3, gap-8)
   - Column 1: Request form card
   - Column 2-3: Management table card
4. Helper text and notes below table

## Interaction Patterns

- Form validation: Inline error messages below fields
- Success feedback: Toast notification or alert banner
- Loading states: Disabled buttons with spinner during submission
- Empty state: Friendly message when no requests exist
- Confirmation dialogs: For approve/reject actions (optional modal)

## Responsive Behavior

**Mobile (< 768px)**
- Stack all elements vertically
- Form takes full width
- Table scrolls horizontally or cards stack
- Buttons remain full-width

**Tablet (768px - 1024px)**
- Two-column grid may collapse to single column
- Table remains scrollable if needed

**Desktop (> 1024px)**
- Full grid layout active
- Optimal spacing and breathing room
- Table displays all columns comfortably

## Accessibility Requirements

- Form labels properly associated with inputs
- ARIA labels for action buttons
- Keyboard navigation for all interactive elements
- Focus indicators on all focusable elements
- Sufficient contrast for all text
- Screen reader friendly status announcements

## Vietnamese Language Considerations

- Ensure proper font rendering for Vietnamese diacritics
- Adequate line-height for proper character spacing (leading-relaxed)
- Test with longer Vietnamese text strings for button/label sizing

## Images
No hero images needed. This is a productivity tool focused on functionality. Icon usage only:
- App logo/icon in header (equipment/box icon)
- Icons for form fields (calendar for date picker)
- Status icons (checkmark, x-mark) in badges