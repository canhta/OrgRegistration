3. Overall User Flows

Below are the three primary organization-creation flows for the prototype. Each flow is described in detail, including decision points, screen transitions, and data inputs.

3.1 Self-Service Registration Flow (Org Admin)

Objective
Allow a prospective Org Admin (e.g., the owner or manager of a yoga studio) to register their organization online without internal assistance. The flow combines account setup, plan selection, location configuration, and a simulated payment step.

Step-by-Step Flow 1. Entry Point
• User arrives at the public TeacherZone landing page URL (e.g., www.teacherzone.com).
• In the top navigation bar or hero section, there is a prominent “Sign Up” button (colored accent—e.g., dark teal) that the user clicks. 2. UI-01: Registration Wizard (Multi-Step)
• The wizard occupies the full browser viewport (desktop layout) and is responsive for tablet/mobile.
• A horizontal progress bar at the top indicates “Step 1 of 3,” “Step 2 of 3,” or “Step 3 of 3,” with the current step highlighted in brand color.
Step 1: Account & Organization Details
• Header: “Create Your TeacherZone Account – Step 1 of 3”
• Sections: 1. Account Information
• Username (Text Input, required)
• Placeholder: “Enter a unique username”
• Validation: Must be 6–20 characters, alphanumeric only; on blur, check uniqueness (simulated).
• Error Message: “Username must be 6–20 characters and contain only letters or numbers.” or “Username already taken.”
• Email Address (Email Input, required)
• Placeholder: “name@example.com”
• Validation: Must match standard email format; check uniqueness on blur.
• Error Message: “Please enter a valid email.” or “An account with this email already exists.”
• Password (Password Input, required)
• Placeholder: “••••••••”
• Validation: Minimum 8 characters, at least one uppercase letter, one lowercase letter, and one number.
• Password Strength Meter: A dynamic indicator (e.g., “Weak,” “Fair,” “Strong”) based on character variety.
• Error Message: “Password must be at least 8 characters and include uppercase, lowercase, and a number.”
• Confirm Password (Password Input, required)
• Placeholder: “••••••••”
• Validation: Must exactly match “Password.”
• Error Message: “Passwords do not match.” 2. Organization Information
• Organization (Business) Name (Text Input, required)
• Placeholder: “e.g., Sunrise Yoga Studio”
• Validation: Non-empty; max 100 characters.
• Error Message: “Organization Name is required.”
• Industry (Dropdown, required)
• Options: “Physical Fitness & Wellness,” “Health & Beauty Services,” “Education & Skill Development,” “Event & Recreational Space Rentals,” “Other.”
• Default Option: “Select an industry….”
• Error Message: “Please select an industry.”
• Checkbox: “My business has multiple locations” (Optional)
• If checked, Step 2 will display multiple location fields; if unchecked, Step 2 displays one location field. 3. Contact & Address Information (US-Only)
• Work Phone (Tel Input, required)
• Placeholder: “e.g., (415) 555-0123”
• Validation: US phone format; auto-format on typing.
• Error Message: “Enter a valid US phone number.”
• Address Line 1 (Text Input, required)
• Placeholder: “Street address, P.O. box, company name, c/o”
• Error Message: “Address Line 1 is required.”
• Address Line 2 (Text Input, optional)
• Placeholder: “Apartment, suite, unit, building, floor, etc.”
• City (Text Input, required)
• Placeholder: “e.g., San Francisco”
• Validation: Alphabetic or alphanumeric; no special characters except hyphens.
• Error Message: “City is required.”
• State (Dropdown, required)
• Options: All 50 U.S. states (e.g., “California,” “New York,” etc.); default: “Select a state…”
• Error Message: “Please select a state.”
• ZIP Code (Text Input, required)
• Placeholder: “e.g., 94103 or 94103-1234”
• Validation: 5-digit or ZIP+4 format (5 digits, or 5 digits + hyphen + 4 digits).
• Error Message: “Enter a valid ZIP code.”
• Country (Dropdown, required)
• Default: “United States” (disabled, since prototype only targets US). 4. Navigation Buttons (Footer of Form)
• [Next: Plan & Locations] (Primary Button, brand-colored)
• Disabled until all required Step 1 fields are valid.
• Hover State: Button darkens slightly on hover.

#### Step 2: Plan Selection & Location Setup

1. **Header**: “Step 2 of 3: Choose Plan & Configure Location(s)” (bold, 20 px).

2. **Subscription Plan Selection**  
   • Three plan cards displayed horizontally with equal width. Each card contains:

   - **Plan Name** (Large, bold text)
   - **Price** (e.g., “$99 / month” or “$1,188 / year” if annual toggle is selected)
   - **Feature Summary** (Bullet list):  
     • “Up to 100 students”  
     • “Basic reporting”  
     • “Email support”
   - **Select Button** (Radio-style selector at top right of card)
   - **Card States**: Unselected: White background, light border; Hover: Light shading; Selected: Solid brand-colored outline with check icon.  
     • **Billing Cycle Toggle**: Above the cards, a toggle switch labeled “Bill Monthly / Bill Annually.” Switching updates the displayed prices.  
     • **Error Handling**: If no plan is selected, display “Please select a subscription plan to continue” below plan cards when trying to proceed.

3. **Location Configuration**  
   • **Intro Text**:

   - If Step 1’s “Multiple Locations” checkbox was **unchecked**, show:  
     “Provide your business’s primary location below.”
   - If **checked**, show:  
      “Add all your business locations below. Click ‘+ Add Another Location’ to include more.”  
     • **Location Group(s)** (each group is a white card with border and padding): For each location:

   1. **Location Name** (Text Input, required)
      - Placeholder: “e.g., Downtown Studio”
      - Error: “Location Name is required.”
   2. **Address Line 1** (Text Input, required)
      - Placeholder: “Street address, etc.”
      - Error: “Address Line 1 is required.”
   3. **Address Line 2** (Text Input, optional)
   4. **City** (Text Input, required)
      - Placeholder: “e.g., Chicago”
      - Error: “City is required.”
   5. **State** (Dropdown, required)
      - Options: 50 states.
      - Error: “Please select a state.”
   6. **ZIP Code** (Text Input, required)
      - Placeholder: “e.g., 60601”
      - Error: “Enter a valid ZIP code.”
   7. **Country** (Dropdown, required)
      - Default: “United States” (disabled).
   8. **Phone** (Tel Input, required)
      - Placeholder: “(312) 555-0187”
      - Error: “Enter a valid phone number.”
   9. **Time Zone** (Dropdown, required)  
       - Options: List of U.S. time zones (e.g., “America/Chicago,” “America/New_York,” etc.).  
       - Error: “Please select a time zone.”  
      • **Remove Location** link (visible if more than one group or multi-location mode):

   - Text: “Remove this location” in red, 12 px; on hover: underline.
   - On click: Confirmation pop-up “Delete Location #n? This cannot be undone.” Buttons: [Delete] [Cancel].  
     • **Add Another Location**
   - Button (secondary, outline, 160 px width, left-aligned): “+ Add Another Location”
   - On click: Append a new location group below with incremented label (Location #2, #3, etc.).  
     • **Minimum Requirement**: At least one location group must be filled out completely (all required fields).

4. **Billing Contact Information**  
   • **Billing Contact Name** (Text Input, required)

   - Placeholder: “Name of billing contact”
   - Error: “Billing Contact Name is required.”  
     • **Billing Contact Email** (Email Input, required)
   - Placeholder: “billing@yourbusiness.com”
   - Error: “Enter a valid email address.”

5. **Payment Information**  
   • **Credit Card Number** (Text Input, required)

   - Placeholder: “1234 5678 9012 3456”
   - Validation: Must match a valid 16-digit credit card format.
   - **Note**: We guarantee that no charges will be applied at this time.
   - Error: “Enter a valid credit card number.”  
     • **Cardholder’s Name** (Text Input, required)
   - Placeholder: “Name as it appears on card”
   - Validation: Non-empty.
   - Error: “Cardholder’s name is required.”  
     • **Expiration Date (MM/YY)** (Text Input, required)
   - Placeholder: “MM/YY”
   - Validation: Must be a valid future expiration in MM/YY format.
   - Error: “Enter a valid expiration date.”  
     • **Security Code (CVV)** (Text Input, required)
   - Placeholder: “123”
   - Validation: Must be a 3- or 4-digit code.
   - Error: “Enter a valid security code.”  
     • **Note**: No charges will be made to the provided credit card during registration.

6. **Simulated Payment Section**  
   • **Instruction Text**: “Click the button below to simulate payment processing for the selected plan (no charges will be applied).”  
   • **[Simulate Payment]** (Primary Button, 180 px width, right-aligned)
   - On click:  
      1. Validate that exactly one plan card is selected.  
      2. Validate that at least one location group is fully filled (all required fields).  
      3. Validate Billing Contact fields.  
      4. Validate Payment Information fields.  
      5. If any validation fails, highlight offending fields in red and show inline error messages.  
      6. If all validation passes, transition to Step 3.  
     • **[Back: Account Details]** (Secondary Button, 100 px width, left-aligned)
   - On click: Return to Step 1, preserving all entered data (persist form state in memory).

Step 3: Confirmation
• Header: “Step 3 of 3: Confirmation”
• Confirmation Message Panel (Green or brand-colored check icon at top left)
• Title: “Registration Complete!”
• Text: “Thank you for registering with TeacherZone. Your organization has been successfully created.”
• Summary Details (Two-column layout): 1. Organization Summary (Left Column)
• Organization Name
• Industry
• Selected Plan (Name + Billing Cycle + Price)
• Billing Contact (Name + Email) 2. Locations Summary (Right Column)
• For each location added:
• Location Name (bold)
• Address (Address Line 1, City, State, ZIP)
• Phone
• Time Zone 3. Next Steps Text (Below summary, full-width)
• “You will be redirected to your Dashboard, where you can complete your profile and begin adding staff, courses, or services.”
• Action Button:
• [Go to Dashboard] (Primary Button, full-width on mobile, right-aligned on desktop)
• On click: Simulate login and navigate to the placeholder Admin Dashboard screen (outside prototype scope, stubbed).

⸻

3.2 Super Admin Direct Organization Creation Flow

3.3 Lead Management Flow

**Objective**
Enable internal CRM staff to capture incoming leads, view and update their details, and convert them into organizations via either sending a registration link or by direct Super Admin creation.

**Step-by-Step Flow**

1. **Entry Point**

   - CRM staff log into the CRM interface (stubbed authentication). They click **"Lead Management"** in the navigation.

2. **UI-08: New Lead Modal**

   - **Modal Header:** "Create New Lead"
   - **Form Fields:**
     - **First Name** (Text Input, required)
     - **Last Name** (Text Input, required)
     - **Email Address** (Email Input, required)
     - **Phone Number** (Tel Input, optional)
     - **Source** (Dropdown, required: Web Form, Facebook Ad, Trade Show, Referral, Other)
     - **Intended Location** (Text Input, required: City, State or specific address)
     - **Assigned Rep** (Dropdown, optional: list of CRM staff)
     - **Initial Stage** (Dropdown, required: New, Contacted, Demo Scheduled, Proposal Sent, Converted, Disqualified)
   - **Action Buttons:**
     - **[Create Lead]:** Validates fields; on success, closes modal and adds lead to the Lead List.
     - **[Cancel]:** Closes modal without saving.

3. **UI-02: Lead List View**

   - Displays a table of all leads with columns:
     - Lead Name
     - Email
     - Phone
     - Source
     - Assigned Rep
     - Stage
     - Intended Location
     - Actions (View, Convert, Disqualify)
   - **Action Buttons (above table):**
     - **[+ New Lead]:** Opens UI-08 modal to create a new lead.
   - **Row Actions:**
     - **[View]:** Opens UI-03 Lead Detail & Timeline.
     - **[Convert]:** Opens a choice to generate a self-service link or open Super Admin creation form (UI-07).
     - **[Disqualify]:** Marks the lead as Disqualified after confirmation.

4. **UI-03: Lead Detail & Timeline**

   - **Header:** Lead’s Full Name, Current Stage, “Back to Lead List” link.
   - **Lead Information Section:**
     - Email, Phone, Source, Assigned Rep, Intended Locations, Custom Fields.
   - **Primary Actions:**
     - **[Send Email]** (opens Send Email modal)
     - **[Send SMS]** (opens Send SMS modal)
     - **[Log Call]** (opens Log Call modal)
     - **[Add Task]** (opens Add Task modal)
     - **[Schedule Demo]** (opens Schedule Demo modal)
     - **[Convert → Self-Service Link]** (opens modal with pre-populated registration URL)
     - **[Convert → Super Admin Creation]** (opens UI-07 with lead data pre-filled)
     - **[Disqualify]** (marks lead as Disqualified)
   - **Timeline Feed:** Chronological list of interactions (emails, SMS, calls, tasks, stage changes), each with icon, description, timestamp, and optional location context.

5. **Conversion Options**

   - **Self-Service Conversion:** Generates a pre-populated registration URL and adds an entry to the lead’s timeline.
   - **Super Admin Conversion:** Opens UI-07 with lead’s information, and on save, creates the organization and updates lead status to Converted.

6. **Result**
   - Converted leads become organizations (Org Admin invited), and their stage is updated accordingly. Disqualified leads are marked and can be archived.

Objective
Allow a TeacherZone super administrator (internal user) to create a new organization, configure one or more physical locations, assign at least one Org Admin user, and set billing/plan/status—all from a single consolidated form.

Step-by-Step Flow 1. Entry Point
• Super Admin logs into the Super Admin Console (stubbed authentication).
• On the left sidebar navigation (collapsed for prototype), the Super Admin clicks “Organizations”.
• A list of existing organizations is displayed (stubbed with placeholder data).
• Super Admin clicks “Create New Organization” (a prominent button at top-right of the list). 2. UI-07: Super Admin – Create/Edit Organization
• The form occupies the main content area, with a header: “Create New Organization.”
• A “Back to Organization List” link is in the top-left corner (breadcrumb style).
Section A: Organization Overview
• Field: Organization Name (Text Input, required)
• Placeholder: “e.g., Sunrise Yoga, Inc.”
• Validation: Non-empty, max 100 characters.
• Error: “Organization Name is required.”
• Field: Primary Industry (Dropdown, required)
• Same options as UI-01’s Industry.
• Error: “Please select an industry.”
• Subsection: Corporate HQ Address
• Address Line 1 (Text Input, required)
• Address Line 2 (Text Input, optional)
• City (Text Input, required)
• Error: “City is required.”
• State (Dropdown, required)
• Options: 50 U.S. states.
• Error: “Please select a state.”
• ZIP Code (Text Input, required)
• Error: “Enter a valid ZIP code.”
• Country (Dropdown, required)
• Default: “United States” (disabled)
• Corporate Phone (Tel Input, optional)
• Corporate Time Zone (Dropdown, required)
• Options: U.S. time zones in IANA format.
• Error: “Time Zone is required.”
• Checkbox: “This organization has multiple locations”
• When toggled ON, Section B expands into a multi-row table interface; when OFF, Section B shows a single-location form.
Section B: Location Setup
• Single-Location Mode (checkbox unchecked)
• Display a form group labeled “Location #1” with: 1. Location Name (Text Input, required)
• Placeholder: “e.g., Downtown Branch”
• Error: “Location Name is required.” 2. Address Line 1, Address Line 2, City, State, ZIP, Country (same validation as Section A) 3. Phone (Tel Input, optional) 4. Time Zone (Dropdown, required)
• Beneath, a note: “Every Organization must have at least one Active location.”
• Multi-Location Mode (checkbox checked)
• Display a table with header columns: “Location Name | City, State | Time Zone | Status | Actions.”
• Initially, one row is shown with example placeholders. Columns for existing data or blank if creating new.
• Actions Column Buttons (per row):
• [Edit] (opens a modal to edit that specific location’s fields).
• [Delete] (prompts confirmation: “Are you sure you want to remove this location? This action cannot be undone.” If confirmed, removes row).
• [+ Add Location] Button below the table (full-width or aligned left).
• On click, opens a modal identical to the “Edit Location” modal, except empty fields.
• Modal Fields: Location Name (required), Address 1 (required), Address 2 (optional), City (required), State (required), ZIP (required), Country (pre-selected US), Phone (optional), Time Zone (required), Status (Dropdown: “Active” or “Inactive”).
• Buttons: [Save Location] [Cancel].
• Validation: same as prior location forms; if errors, show inline.
• In the table, the “Status” column can reflect “Active” or “Inactive” with a colored badge (green for Active, gray for Inactive).
• Minimum Requirement: At least one location must have Status = “Active” before saving.
Section C: Assign Org Admin
• Intro Text: “An Organization Administrator will manage this organization’s account and locations.”
• Fields (at least one group required): 1. First Name (Text Input, required)
• Placeholder: “e.g., Alice”
• Error: “First Name is required.” 2. Last Name (Text Input, required)
• Placeholder: “e.g., Nguyen”
• Error: “Last Name is required.” 3. Email Address (Email Input, required)
• Placeholder: “e.g., alice@sunriseyoga.com”
• Validation: valid email format.
• Error: “Enter a valid email address.” 4. Temporary Password (Password Input, required)
• Auto-generate a strong password (e.g., “Ab3$kLp9”) by default; user can override if desired.
• Validation: same as UI-01 password rules.
• Error: “Password must be at least 8 characters and include uppercase, lowercase, and a number.” 5. Checkbox: “Send invitation email upon saving”
• If checked, once the Organization is saved, send a simulated email to Org Admin with a link to set their permanent password.
• Link/Button: “+ Add another Org Admin”
• When clicked, appends a second set of First Name, Last Name, Email, Temporary Password, and checkbox fields.
• Note: If multiple Org Admins are added, each must have a unique email.
Section D: Plan & Initial Status
• Dropdown: Subscription Plan (required)
• Options: GROWING ($99/month), ESTABLISHED ($225/month), ENTERPRISE (Custom).
• Default placeholder: “Select a plan…”
• Error: “Please select a subscription plan.”
• Radio Buttons: Initial Account Status (required)
• Active (Immediately active, assume billing is handled later).
• Trial (Free trial for X days).
• Pending Payment (Organization cannot access features until payment is collected).
• Conditional Field (if “Trial” selected):
• Trial Period (Days) (Numeric Input, required)
• Default: 14 days.
• Validation: Minimum 1, maximum 90.
• Error: “Enter a valid trial period (1–90 days).”
Action Buttons (Footer)
• [Save & Invite Org Admin] (Primary Button)
• On click: 1. Validate all required fields across Sections A–D. 2. If any validation errors, highlight fields and display inline messages. 3. If valid, create Organization, Location(s), and User(s) (Org Admin). 4. If “Send invitation email” checked for any Org Admin, simulate sending an email with text:
• “Hello [Org Admin Name], you have been invited to manage [Organization Name]. Please click here to set your password and log in.”
• Then redirect to UI-09: Organization Detail & Locations (Overview tab) for the newly created organization.
• [Cancel] (Secondary Button)
• Discard all input data and return to the Super Admin’s Organization List screen (stubbed). 3. UI-09: Super Admin – Organization Detail & Locations
• Header: “Organization Details” with an edit icon next to the name.
• Tabs (horizontal navigation below header): 1. Overview
• Summary Cards (two or three columns on desktop, stacked on mobile):
• Organization Info: Name, Industry, Status (Active/Trial/Pending), Plan, Corporate Phone, Corporate Time Zone.
• Location Count: Number of Active Locations (e.g., “3 Active Locations”) with a “View Locations” link.
• Org Admins: List Org Admin names & emails, with invitation status (“Active” or “Invited”). If any Org Admin has not yet accepted, show a “Resend Invitation” link next to their name.
• Action Buttons (top-right):
• [Edit Organization] → Opens UI-07 in “Edit Mode” (fields pre-populated).
• [Deactivate Organization] (only if Status = Active or Trial). Confirmation modal: “Are you sure? This will log out all Org Admins and freeze account.” 2. Locations
• Table Columns: “Location Name | Address | Time Zone | Status | Active Students | Next Scheduled Class | Actions”
• Location Name (clickable to open a Location-specific dashboard stub).
• Address (e.g., “123 Main St, Chicago, IL 60601”).
• Time Zone (e.g., “America/Chicago”).
• Status (Badge: Green “Active” or Gray “Inactive”).
• Active Students (Number badge—e.g., “24”).
• Next Scheduled Class (Date/Time—e.g., “06/10/2025, 9:00 AM”).
• Actions: Buttons [Edit] (opens the same location modal as UI-07 Section B but in edit mode), [Deactivate] (confirmation modal: “Deactivate this location?”).
• [+ Add Location] Button (top-right above table)
• Opens the “Add Location” modal from UI-07 Section B. 3. Org Admins
• Table Columns: “Name | Email | Role | Status | Last Login | Actions”
• Name (e.g., “Alice Nguyen”)
• Email (e.g., “alice@example.com”)
• Role (always “Organization Admin” in this context)
• Status: “Active” (green badge) or “Invited” (orange badge) if the invited admin has not set a password.
• Last Login: Date/time or “Never” if not yet logged in.
• Actions: [Resend Invitation] if status = Invited; [Remove Admin] (confirmation modal: “Remove this Admin? They will lose access immediately.”)
• [Invite New Org Admin] Button (top-right)
• Opens a small modal with fields: First Name, Last Name, Email, Temporary Password (auto-generated), Checkbox: “Send invitation email.” Then [Save] or [Cancel]. 4. Billing & Status
• Display:
• Current Plan (Name + Billing Cycle + Price; e.g., “ESTABLISHED – $225/mo”).
• Next Billing Date (e.g., “07/01/2025”).
• Account Status: “Active” (green badge), “Trial – 10 days remaining” (blue badge), or “Pending Payment” (red badge).
• [Update Plan & Status] Button (opens a modal with: 1. Plan Dropdown (same options as UI-07 Section D). 2. Status Radio Buttons (Active, Trial, Pending). 3. If Trial selected, Trial Period (numeric). 4. Buttons: [Save] [Cancel].
• Error Validation: If switching to “Trial,” ensure Trial Period is ≥1 day; if switching to “Pending Payment,” show a note: “This organization will not be able to access features until payment is confirmed.”

⸻

4. Detailed Business & Functional Requirements

Below are the functional requirements for each prototype feature, described in business-focused language. Technical/APIs are excluded; the emphasis is on what each screen and flow must accomplish.

4.1 Organization Registration & Creation (FR-ORG)

FR-ORG-01: Self-Service Registration Wizard
• Must guide a new Org Admin through a three-step process (UI-01).
• Validation: All required fields must be filled before proceeding. Inline error messages must appear under invalid fields.
• Conditional Display: If user indicates “multiple locations” in Step 1, Step 2 must allow adding more than one location. Otherwise, only one location is required.
• Simulated Payment: For prototype, clicking “Simulate Payment” in Step 2 suffices; no real payment processing.
• Success Transition: After Step 2 validated and “Simulate Payment” clicked, display Step 3 with summary details and a “Go to Dashboard” button. Assume user is automatically logged in.

FR-ORG-02: Super Admin Direct Creation
• Accessible exclusively by a Super Admin role (role enforcement stubbed).
• One form (UI-07) must handle both single-location and multi-location scenarios.
• Location Constraints: At least one location must be created. Each location requires a name, address, and time zone.
• Org Admin Assignment: Must assign at least one Org Admin user. Each Org Admin needs first name, last name, email, and temporary password. Optionally, multiple Org Admins can be invited at once.
• Invitation Mechanism: Checking “Send invitation email” triggers a simulated email to that Org Admin’s address containing a password reset link (stubbed).
• Plan & Status: Must select a subscription plan and set initial status to Active, Trial (with specified days), or Pending Payment.
• Post-Save Behavior: After saving, redirect to UI-09 (Organization Detail & Locations) for review and further edits.

FR-ORG-03: Multi-Location Support
• Every organization has one or more location child entities.
• When “multiple locations” is indicated:
• Super Admin and Org Admin can add, edit, or deactivate each location independently.
• Self-Service users can add multiple location groups in Step 2 of the wizard.
• Each location has: Name, Address (line1, line2, city, state, ZIP, country), Phone, Time Zone, and Status (Active/Inactive).
• The dashboard (not detailed) will display each location’s key metrics separately under the same organization umbrella.

⸻

4.3 Role Definitions & Permissions (FR-ROLE)

For the prototype, roles and permissions are enforced logically (no actual authentication/authorization). Each role sees and can interact only with specific screens and UI elements:

1. Super Admin
   • Access:
   • Super Admin Console (stubbed as a top-level menu).
   • UI-07 (Create/Edit Organization).
   • UI-09 (Organization Detail & Locations).
   • Cannot simulate actual user logins for Org Admins (invitation stub only).
2. Org Admin
   • Access (after self-service registration or invitation from Super Admin):
   • Dashboard (stubbed lead to a placeholder dashboard with “Welcome, [Name]” and a link to “Manage Locations” which leads to UI-09 Locations tab).
   • UI-09 Organization Detail & Locations (only for their own organization).
   • Can view and edit location details (via “Edit” in Locations tab).
   • Cannot access CRM pipeline in the prototype.

⸻

5. Screen Specifications (Detailed)

Below are detailed descriptions of every screen, including all input fields, labels, validation rules, button states, and expected behaviors. This level of detail ensures designers and developers understand exactly what to build for the prototype.

5.1 UI-01: Registration Wizard (Multi-Step)

General Layout
• Full-width container with a maximum content width of 960 px, centered horizontally.
• Background: Light gray (#F5F7FA) behind the form, which sits on a white card (#FFFFFF) with slight shadow.
• Top: Horizontal progress bar (three bullets labeled 1, 2, 3; the current bullet filled with brand-color, others outlined).
• Beneath progress bar: Step title (e.g., “Step 1 of 3: Account & Organization Details”) in bold 20 px font.
• Form area has adequate vertical spacing (24 px) between fields and logical grouping with section headings.

⸻

Step 1: Account & Organization Details 1. Header Text
• “Create Your TeacherZone Account – Step 1 of 3” (bold, 20 px, center-aligned above the form). 2. Account Information Section (boxed in a faint border with slight rounding)
• Username:
• Label: “Username _”
• Input: Text, width 100% of form group.
• Placeholder: “Enter a unique username.”
• Validation on blur:
• Must be 6–20 alphanumeric characters.
• Simulate asynchronous “Username available?” check (display a spinner for 500 ms, then success or failure).
• If invalid or taken, outline in red and show inline error: “Username must be 6–20 characters and contain only letters or numbers.” or “That username is already taken.”
• Email Address:
• Label: “Email Address _”
• Input: Email type, width 100%.
• Placeholder: “name@example.com.”
• Validation: If not valid email format, red outline, error: “Enter a valid email address.” If already in use, error: “An account with this email already exists.”
• Password:
• Label: “Password _”
• Input: Password type, width 100%.
• Placeholder: “••••••••”
• Strength Meter: Below input, a light gray bar that fills with green portions as user types varied characters. Strength labels appear: “Weak,” “Fair,” “Strong.”
• Validation on blur:
• Must be at least 8 characters, contain at least one uppercase letter, one lowercase letter, and one digit.
• If invalid: red outline, error: “Password must be at least 8 characters and include uppercase, lowercase, and a number.”
• Confirm Password:
• Label: “Confirm Password _”
• Input: Password type, width 100%.
• Placeholder: “••••••••”
• Validation: Must match “Password” exactly. If mismatch: red outline, error: “Passwords do not match.” 3. Organization Information Section (margin-top: 32 px)
• Label: “Organization Details” (bold 16 px).
• Organization Name:
• Label: “Organization (Business) Name _”
• Input: Text, width 100%.
• Placeholder: “e.g., Sunrise Yoga Studio”
• Validation: Non-empty; if empty, error: “Organization Name is required.”
• Industry:
• Label: “Industry _”
• Dropdown: width 100%.
• Default Option: “Select an industry…” (gray text).
• Options: “Physical Fitness & Wellness,” “Health & Beauty Services,” “Education & Skill Development,” “Event & Recreational Space Rentals,” “Other.”
• Validation: If default selected, error: “Please select an industry.”
• Checkbox: “My business has multiple locations”
• Checkbox input left of label.
• When checked, update Step 2 to allow multiple location entries.
• No validation here (optional).
• Contact & Address (US-Only) (margin-top: 24 px) 1. Work Phone:
• Label: “Work Phone _”
• Input: Tel, width 100%.
• Placeholder: “(415) 555-0123”
• On blur: Validate 10-digit U.S. format. If invalid, red outline, error: “Enter a valid US phone number.” 2. Address Line 1:
• Label: “Address Line 1 _”
• Input: Text, width 100%.
• Placeholder: “Street address, P.O. box, etc.”
• Validation: Non-empty; if empty, error: “Address Line 1 is required.” 3. Address Line 2:
• Label: “Address Line 2 (optional)”
• Input: Text, width 100%. 4. City:
• Label: “City _”
• Input: Text, width 100%.
• Placeholder: “e.g., San Francisco”
• Validation: Non-empty; if empty, error: “City is required.” 5. State:
• Label: “State _”
• Dropdown, width 100%.
• Default: “Select a state…”
• Options: All 50 U.S. states in alphabetical order.
• Validation: If default, error: “Please select a state.” 6. ZIP Code:
• Label: “ZIP Code _”
• Input: Text, width 100%.
• Placeholder: “e.g., 94103 or 94103-1234”
• Validation: Must match 5-digit or ZIP+4 format. If invalid, error: “Enter a valid ZIP code.” 7. Country:
• Label: “Country _”
• Dropdown, width 100%, default “United States” (disabled). 4. Navigation Buttons (fixed at bottom of the form card with a subtle top border):
• [Next: Plan & Locations] (Primary Button, width 160 px, aligned right)
• Disabled until all required fields in Step 1 pass validation.
• Hover state: Slight darkening.
• On click: Transition to Step 2 (smooth fade animation).
• No “Back” button on Step 1 (first step).

⸻

Step 2: Plan Selection & Location Setup 1. Header: “Step 2 of 3: Choose Plan & Configure Location(s)” (bold, 20 px). 2. Subscription Plan Selection (boxed section with card layout)
• Billing Cycle Toggle (centered above plan cards):
• Label: “Billing Cycle:”
• Toggle Switch:
• Left: “Monthly” (default selected), Right: “Annually.”
• When toggled to “Annually,” plan card prices update (e.g., “$1,188 / year” for GROWING).
• Plan Cards (display three cards side by side with equal width; each card responsive to shrink to two or one column on smaller viewports):
• Card Container:
• White background (#FFFFFF), border radius 8 px, border 1 px light gray (#E0E0E0), box shadow (0 px 2 px 4 px rgba(0,0,0,0.05)).
• Padding: 24 px.
• Margin: 8 px between cards.
• Card Content (vertical stack): 1. Plan Name (16 px bold, centered) 2. Price (24 px bold, center; e.g., “$99 / month” or “$1,188 / year”) 3. Feature List (unordered list of bullet points, 14 px):
• “Up to 100 students”
• “Basic reporting”
• “Email support” 4. Select Radio Button (position top-right inside card):
• Outer circle (18 px diameter).
• When unselected: gray outline, white fill; when selected: brand-color fill with check icon.
• Hover: entire card border darkens slightly. 5. “Best Value” Ribbon (optional for annual mode on ESTABLISHED plan):
• Diagonal ribbon in top-left corner, colored gold, with text “Best Value.”
• Error Handling: If no plan card is selected and the user attempts to proceed, display inline text below cards: “Please select a subscription plan to continue.” 3. Location Configuration
• Instruction Text:
• If Step 1 “Multiple Locations” was unchecked:
“Provide your business’s primary location below.”
• If checked:
“Add all your business locations below. Click ‘+ Add Another Location’ to include more.”
• Location Group(s) (each group is a white card with border and padding):
• Single-Location Mode (unchecked): Display exactly one location group labeled “Location #1.”
• Multi-Location Mode (checked): Display a minimum of one location group; allow adding new groups. Label groups “Location #1,” “Location #2,” etc.
• Fields (each inside a two-column grid when viewport ≥ 768 px, single-column stacked on mobile): 1. Location Name (Text Input, required)
• Placeholder: “e.g., Downtown Studio”
• Error: “Location Name is required.” 2. Address Line 1 (Text Input, required)
• Placeholder: “Street address, etc.”
• Error: “Address Line 1 is required.” 3. Address Line 2 (Text Input, optional) 4. City (Text Input, required)
• Placeholder: “e.g., Chicago”
• Error: “City is required.” 5. State (Dropdown, required)
• Options: 50 states.
• Error: “Please select a state.” 6. ZIP Code (Text Input, required)
• Placeholder: “e.g., 60601”
• Error: “Enter a valid ZIP code.” 7. Country (Dropdown, required)
• Default: “United States” (disabled). 8. Phone (Tel Input, required)
• Placeholder: “(312) 555-0187”
• Error: “Enter a valid phone number.” 9. Time Zone (Dropdown, required)
• Options: List of U.S. time zones (e.g., “America/Chicago,” “America/New_York,” etc.).
• Error: “Please select a time zone.”
• Remove Location Link (visible if more than one group or if multi-location box was checked)
• Text: “Remove this location” in red, 12 px.
• On hover: underline.
• On click: Confirmation pop-up “Delete Location #n? This cannot be undone.” Buttons [Delete] [Cancel].
• Add Another Location
• Button (secondary style, outline, 160 px width, left-aligned under location groups).
• Text: “+ Add Another Location.”
• On click: Append a new location group below with incremented label (Location #2, #3, etc.) 4. Billing Contact Information
• Billing Contact Name (Text Input, required)
• Placeholder: “Name of billing contact”
• Validation: Non-empty; if empty, error: “Billing Contact Name is required.”
• Billing Contact Email (Email Input, required)
• Placeholder: “billing@yourbusiness.com”
• Validation: valid email format; if invalid, error: “Enter a valid billing email.” 5. Simulated Payment Section
• Instruction Text: “Click the button below to simulate payment processing for the selected plan.”
• [Simulate Payment] (Primary Button, 180 px width, right-aligned)
• On click: 1. Validate that exactly one plan card is selected. 2. Validate that at least one location group is fully filled (all required fields). 3. Validate Billing Contact fields. 4. If any validation fails, highlight offending fields in red and show inline error messages. 5. If all validation passes, transition to Step 3.
• [Back: Account Details] (Secondary Button, 100 px width, left-aligned next to Simulate Payment)
• On click: Return to Step 1, preserving all entered data (persist form state in memory).

⸻

Step 3: Confirmation 1. Header: “Step 3 of 3: Confirmation” (bold, 20 px). 2. Confirmation Panel (centered within card, green background accent, white text):
• Icon: Large checkmark (✓) in a green circle at top.
• Title: “Registration Complete!” (24 px bold)
• Description:
“Thank you for registering your organization with TeacherZone. Your account is now active, and you can start setting up your business.” 3. Summary Details (two-column grid on desktop, stacked on mobile)
• Left Column: Organization Summary:
• Organization Name: “Sunrise Yoga Studio” (bold, 16 px)
• Industry: “Physical Fitness & Wellness” (14 px)
• Selected Plan: “ESTABLISHED ($225/month)” (14 px)
• Billing Contact: “Alice Nguyen – alice@sunriseyoga.com” (14 px)
• Right Column: Locations Summary: For each location:
• Location Name (bold, 14 px)
• Address: “123 Main St, Chicago, IL 60601” (14 px)
• Phone: “(312) 555-0187” (14 px)
• Time Zone: “America/Chicago” (14 px)
• Separator: 8 px vertical space between location blocks. 4. Next Steps Text (full-width, center-aligned below summary):
• “You will be redirected to your Dashboard, where you can complete your profile, add staff, and start setting up your classes or services. Welcome aboard!” 5. Action Buttons (footer area)
• [Go to Dashboard] (Primary Button, 200 px width, right-aligned)
• On click: Simulate logging in and transition to the Admin Dashboard (stubbed).
• No “Back” button on Step 3.

⸻

Right Column 1. Lead Profile Summary (Sticky Card)
• White background, padding 16 px, border radius 6 px, slight shadow. Always visible while left column scrolls.
• Avatar Placeholder (circular, 80 px diameter), either blank or with initials “JD.”
• Name & Title (centered below avatar):
• “John Doe” (18 px bold)
• “Prospect Lead” (12 px, gray)
• Contact Info (two rows, left-aligned):
• Email: clickable, 14 px
• Phone: clickable, 14 px
• Source: “Facebook Ad” (14 px)
• Assigned Rep: “Alice Nguyen” (14 px)
• Lead Score: “N/A” or static “75/100” (14 px, bold) 2. Quick Actions (Card below Profile Summary)
• Toggle: “Auto-nurture Campaign” (ON/OFF switch)
• If toggled ON: show text “Lead is enrolled in an auto-nurture sequence.”
• If OFF: show “Lead is not currently in an auto-nurture sequence.”
• Button: “Add to Nurture Sequence” (Secondary button)
• Opens a stub modal: “Nurture sequence creation coming soon.”
• Button: “Link to Existing Organization” (Secondary)
• Opens a search modal to find an existing organization by name or location (stub: search input + “Link” button).
• Location Tags
• Display each intended location as a pill (e.g., “Chicago, IL” pill, 12 px text, light gray background, small “×” to remove).

⸻

5.5 UI-07: Super Admin – Create/Edit Organization

General Layout
• Sidebar navigation on left (collapsed to icons in prototype).
• Main content area width 80% of viewport, with a page header at top.
• Page Header: “Super Admin > Organizations > Create New Organization” (breadcrumb).

Section A: Organization Overview (White Card)
• Card Header: “Organization Overview” (bold, 16 px).
• Fields (laid out in a two-column grid on desktop, single-column on mobile): 1. Organization Name (Text Input, required)
• Label: “Organization Name _”
• Placeholder: “e.g., Sunrise Yoga, Inc.”
• Error: “Organization Name is required.” 2. Primary Industry (Dropdown, required)
• Label: “Primary Industry _”
• Default: “Select an industry…”
• Options: same as UI-01.
• Error: “Please select an industry.” 3. Corporate HQ Address (address sub-grid, two columns inside this cell):
• Address Line 1 (Text Input, required)
• Error: “Address Line 1 is required.”
• Address Line 2 (Text Input, optional)
• City (Text Input, required)
• Error: “City is required.”
• State (Dropdown, required)
• Error: “Please select a state.”
• ZIP Code (Text Input, required)
• Error: “Enter a valid ZIP code.”
• Country (Dropdown, default: “United States,” disabled) 4. Corporate Phone (Tel Input, optional)
• Validation: if provided, must be US format.
• Error: “Enter a valid phone number.” 5. Corporate Time Zone (Dropdown, required)
• Label: “Corporate Time Zone \*”
• Options: U.S. time zones.
• Error: “Please select a time zone.”
• Checkbox: “This organization has multiple locations” (below address group, full-width)
• On toggle, show or hide Section B’s multi-location table interface—see below.

Section B: Location Setup (White Card, margin-top 16 px)
• If Single-Location Mode (checkbox unchecked)
• Card Header: “Primary Location” (bold, 16 px)
• Fields (similar to UI-01 Step 2 location group) in two-column grid: 1. Location Name (Text Input, required)
• Error: “Location Name is required.” 2. Address Line 1 (Text Input, required)
• Error: “Address Line 1 is required.” 3. Address Line 2 (Text Input, optional) 4. City (Text Input, required)
• Error: “City is required.” 5. State (Dropdown, required)
• Error: “Please select a state.” 6. ZIP Code (Text Input, required)
• Error: “Enter a valid ZIP code.” 7. Country (Dropdown, required, default: “United States,” disabled) 8. Phone (Tel Input, optional)
• Error: “Enter a valid phone number.” 9. Time Zone (Dropdown, required)
• Error: “Please select a time zone.”
• Note: “Every organization must have at least one active location.”
• If Multi-Location Mode (checkbox checked)
• Card Header: “Locations” (bold, 16 px)
• Locations Table:
• Columns: 1. Location Name (Clickable text linking to edit modal) 2. City, State (text) 3. Time Zone (text) 4. Status (Badge: “Active” in green or “Inactive” in gray) 5. Actions (two small icon buttons: [Edit] pencil icon, [Delete] trash icon)
• Row Height: 48 px; text 14 px; zebra striping (white / #F9FAFB).
• [+ Add Location] Button (below table, left-aligned, secondary style):
• On click: Open “Add Location” modal (detailed below).
• Add/Edit Location Modal
• Header: “Add/Edit Location” (bold 18 px), close icon (×).
• Fields (two-column on desktop): 1. Location Name _ (Text Input)
• Error: “Location Name is required.” 2. Address Line 1 _ (Text Input)
• Error: “Address Line 1 is required.” 3. Address Line 2 (Text Input) 4. City _ (Text Input)
• Error: “City is required.” 5. State _ (Dropdown)
• Error: “Please select a state.” 6. ZIP Code _ (Text Input)
• Error: “Enter a valid ZIP code.” 7. Country (Dropdown, default: “United States,” disabled) 8. Phone (Tel Input)
• Error: “Enter a valid phone number.” 9. Time Zone _ (Dropdown)
• Error: “Please select a time zone.” 10. Status \* (Dropdown): Options: “Active,” “Inactive.”
• Error: “Please select a status.”
• Action Buttons (footer):
• [Save Location] (Primary)
• [Cancel] (Secondary)
• Behavior: On Save, validate fields; if valid, close modal and update table row in Section B. If not valid, highlight errors. On Cancel, close modal without saving.

Section C: Assign Org Admin (White Card, margin-top 16 px)
• Card Header: “Assign Organization Administrator(s)” (bold, 16 px)
• Instruction Text (below header):
“At least one Organization Administrator is required. An Org Admin can manage this organization’s settings and locations.” (14 px, gray).
• Org Admin Entry Group(s) (repeatable group – at least one required): 1. First Name _ (Text Input)
• Placeholder: “e.g., Alice”
• Error: “First Name is required.” 2. Last Name _ (Text Input)
• Placeholder: “e.g., Nguyen”
• Error: “Last Name is required.” 3. Email Address _ (Email Input)
• Placeholder: “alice@example.com”
• Validation: Valid email format.
• Error: “Enter a valid email address.” 4. Temporary Password _ (Password Input)
• Placeholder: “••••••••” (auto-filled with generated value, editable).
• Validation: Same as UI-01 password rules.
• Error: “Password must be at least 8 characters and include uppercase, lowercase, and a number.” 5. Checkbox: “Send invitation email upon saving” (default: checked)
• Link: “+ Add another Org Admin” (below first group)
• On click: Append a duplicate Org Admin entry group with blank fields.
• Behavior: Must have at least one Org Admin entry group filled completely (all four required fields are valid). If any email duplicates another either in the group or as an existing Org Admin, show error: “Email address already in use.”

Section D: Plan & Initial Status (White Card, margin-top 16 px)
• Card Header: “Plan & Account Status” (bold, 16 px)
• Fields (two-column grid): 1. Subscription Plan _ (Dropdown)
• Label: “Subscription Plan _”
• Default: “Select a plan…”
• Options: “GROWING ($99/mo),” “ESTABLISHED ($225/mo),” “ENTERPRISE (Custom).”
• Error: “Please select a subscription plan.” 2. Initial Status _ (Radio Buttons)
• Label: “Initial Account Status _”
• Options: “Active,” “Trial,” “Pending Payment.”
• Error: “Please select an account status.” 3. Conditional: Trial Period (Days) (Numeric Input)
• Label: “Trial Period (Days) \*” (only visible if “Trial” is selected)
• Placeholder: “14”
• Validation: Must be between 1 and 90.
• Error: “Enter a valid trial period (1–90 days).”

⸻

Action Buttons (Footer of Entire Form UI-07)
• [Save & Invite Org Admin] (Primary Button, right-aligned, 200 px width)
• On click: 1. Validate all required fields in Sections A–D. 2. If any validation errors, highlight fields with inline messages and do not submit. 3. If valid, simulate creation of Organization and Location(s), create Org Admin user(s), and simulate sending invitation emails (pop-up: “Invitation sent to [email address].”). 4. Redirect to UI-09: Organization Detail & Locations (Overview tab) with newly created data displayed.
• [Cancel] (Secondary Button, left of Save)
• On click: Show confirmation “Discard all changes?” with buttons [Yes, Discard] and [No, Continue Editing]. On confirming discard, return to Super Admin’s Organization List screen (stubbed).

⸻

5.6 UI-09: Super Admin – Organization Detail & Locations

General Layout
• Sidebar on left (collapsed or icon-only, not interactive in prototype).
• Header Bar across top of main content area:
• Breadcrumb: “Super Admin > Organizations > [Organization Name]” (Organization Name bold).
• Action Buttons (right side of header):
• [Edit Organization] (Primary)
• [Deactivate Organization] (Danger, only if Status = Active/Trial).

Tabs (Below Header) 1. Overview Tab (default)
• Summary Cards (three cards side by side on desktop, stacked on mobile): 1. Organization Info Card (white background, padding 16 px, border radius 8 px):
• Title: “Organization Info” (bold, 16 px)
• Details (list format, 14 px):
• Name: Sunrise Yoga, Inc.
• Industry: Physical Fitness & Wellness
• Status: Active (green badge)
• Plan: ESTABLISHED ($225/mo)
• Corporate Phone: (312) 555-0187
• Time Zone: America/Chicago 2. Location Count Card:
• Title: “Locations” (bold, 16 px)
• Value: “3 Active Locations” (bold, 24 px)
• Link: “View Locations” (blue link, 14 px) that navigates to Locations tab. 3. Org Admins Card:
• Title: “Organization Administrators” (bold, 16 px)
• List (14 px):
• Alice Nguyen – Active (last login: 06/05/2025)
• Bob Smith – Invited (no login yet), with a “Resend Invitation” link next to Bob’s entry. 2. Locations Tab
• Table Header Row (bold 14 px, background #F3F4F6):
• Columns: “Location Name | Address | Time Zone | Status | Active Students | Next Class | Actions”
• Table Rows (data rows alternating white and very light gray #FAFAFA):
• Location Name (clickable text, 14 px) e.g., “Downtown Studio.” On hover: underline.
• Address (14 px) e.g., “123 Main St, Chicago, IL 60601”
• Time Zone (14 px) e.g., “America/Chicago”
• Status: Badge (Active = green, Inactive = gray)
• Active Students: Numeric badge (blue background, white text) e.g., “24”
• Next Class: “06/10/2025, 9:00 AM” (14 px) or “N/A” if none
• Actions:
• [Edit] (pencil icon, 16 px, clickable)
• [Deactivate] (trash icon, 16 px, clickable)
• On clicking Deactivate: confirmation modal “Deactivate this location?” [Yes], [Cancel].
• [+ Add Location] Button (primary, 160 px, above table aligned right).
• On click: opens “Add Location” modal (same as UI-07 Section B). 3. Org Admins Tab
• Table Header: “Name | Email | Status | Last Login | Actions”
• Rows:
• Alice Nguyen | alice@sunriseyoga.com | Active (green badge) | 06/05/2025, 3:12 PM | [Remove] (trash icon)
• Bob Smith | bob@sunriseyoga.com | Invited (orange badge) | Never | [Resend Invite] (mail icon), [Remove] (trash icon)
• [Resend Invite]: on click, simulation pop-up: “Invitation email resent to bob@sunriseyoga.com.”
• [Remove]: confirmation “Remove this Org Admin? [Yes] [Cancel].”
• [Invite New Org Admin] Button (above table, right-aligned).
• Opens a small modal with fields: First Name, Last Name, Email, Temporary Password, Checkbox “Send invitation email.” 4. Billing & Status Tab
• Card (white background) with two sections: 1. Current Plan & Billing (bold 16 px):
• Plan: “ESTABLISHED ($225/month)”
• Next Billing Date: “07/01/2025”
• Account Status: “Active” (green badge) or “Trial – 10 days remaining” (blue badge) or “Pending Payment” (red badge)
• [Update Plan & Status] Button (primary) that opens a modal:
• Plan Dropdown (same options as creation)
• Status Radio Buttons (Active, Trial with Trial Period input, Pending Payment)
• [Save] (primary), [Cancel]
• Validation: if “Trial” selected, Trial Period (≥1 day) is required.
• On Save: show simulation “Plan and status updated successfully.” 2. Billing Contact (bold 14 px, below first section):
• Billing Contact Name: “Alice Nguyen”
• Billing Contact Email: “billing@sunriseyoga.com”
• Billing Address: “123 Corporate Ave, Suite 400, Chicago, IL 60601”
• [Update Billing Info] Button (secondary) opens a modal (outside prototype scope).