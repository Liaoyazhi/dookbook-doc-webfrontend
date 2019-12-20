TOPICS: hidden attribute
AUTHORS: mdn; mdn@mozilla-community.org; github:mdn

# HTML Global Attribute: `hidden`

The **`hidden`** [global attribute](/en/webfrontend/HTML_Global_Attributes) is a Boolean attribute
indicating that the element is not yet, or is no longer, relevant. For example, it can be used to
hide elements of the page that can't be used until the login process has been completed. Browsers
won't render elements with the hidden attribute set.

The hidden attribute must not be used to hide content just from one presentation. If something is
marked hidden, it is hidden from all presentations, including, for instance, screen readers.

Hidden elements shouldn't be linked from non-hidden elements, and elements that are descendants of a
hidden element are still active, which means that script elements can still execute and form elements
can still submit. Elements and scripts may, however, refer to elements that are hidden in other contexts.

For example, it would be incorrect to use the href attribute to link to a section marked with the
hidden attribute. If the content is not applicable or relevant, then there is no reason to link to it.

It would be fine, however, to use the ARIA `aria-describedby` attribute to refer to descriptions that
are themselves hidden. While hiding the descriptions implies that they are not useful on their own,
they could be written in such a way that they are useful in the specific context of being referenced
from the element that they describe.

Similarly, a canvas element with the hidden attribute could be used by a scripted graphics engine as
an off-screen buffer, and a form control could refer to a hidden form element using its form attribute.

!!! warn "Don't try this at home"
    **Note**: Changing the value of the CSS display property on an element with the hidden attribute
    overrides the behavior. For instance, elements styled display: flex will be displayed despite the
    hidden attribute's presence.

## See also

- All HTML [global attributes](/en/webfrontend/HTML_Global_Attributes).
- [`aria-hidden attribute`](/en/webfrontend/aria-hidden_attribute)
