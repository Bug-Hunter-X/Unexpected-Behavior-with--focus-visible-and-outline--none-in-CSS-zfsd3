# Unexpected Behavior with :focus-visible and outline: none in CSS

This repository demonstrates a subtle bug related to the use of the CSS `:focus-visible` pseudo-class in conjunction with the `outline: none` style.  The bug occurs when `outline: none` is applied in a way that overrides the styling within the `:focus-visible` rule, leading to accessibility issues.

## Bug Description

The `:focus-visible` pseudo-class is designed to show a focus indicator only when the element receives focus using the keyboard or assistive technologies, and not when clicked with a mouse. However, if `outline: none` is applied globally or with higher specificity than the `:focus-visible` rule, the focus indicator will be removed completely, even when using keyboard navigation.

## How to Reproduce

1. Clone this repository.
2. Open `bug.css` to see the problematic code.
3. Create an HTML file with a text input element.
4. Apply the styles in `bug.css`.
5. Observe that the focus indicator does not appear when navigating the input with the keyboard.

## Solution

Refer to `bugSolution.css` for a corrected version of the CSS.  The solution ensures that the `:focus-visible` styling is applied with sufficient specificity to override the `outline: none` rule.  Avoiding the global application of `outline: none` is also a key aspect of the solution.

## Accessibility Considerations

This bug highlights the importance of careful CSS specificity and the correct usage of the `:focus-visible` pseudo-class.  Failure to properly implement `:focus-visible` can lead to accessibility problems for users who rely on visual focus indicators for navigation.