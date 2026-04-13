# Welcome to the Nano-Design Group Website Source!

## Quick Start
- Install Ruby, Bundle, and Jekyll
- `bundle install`
- `bundle exec jekyll serve` in this directory to see changes locally at `http://localhost:4000`

## How to Update Content

### 1. People & Profiles
To add yourself or update your bio:
- Navigate to `_people/`.
- Create a new Markdown file (e.g., `your-name.md`).
- Use the following Front Matter:
  ```markdown
  ---
  layout: bio
  person_id: uniqueid
  name: Your Full Name
  role: Your Role (e.g., Undergraduate Researcher, Graduate Researcher, Postdoctoral Researcher, Principle Investigator)
  email: your.email@example.com  # Optional
  linkedin: https://www.linkedin.com/in/your-linkedin-username  # Optional - full URL
  google_scholar: https://scholar.google.com/citations?user=YOUR_ID  # Optional - full URL
  image: /assets/images/your_headshot.jpg
  ---
  Your bio content goes here...
  ```
- **Note:** `email`, `linkedin`, and `google_scholar` are optional—only include them if you want them displayed.

### 2. Research Projects
To add a new project:
- Navigate to `_projects/`.
- Create a new Markdown file.
- **For an Umbrella (Thrust):** set `is_umbrella: true`.
- **For a Sub-project:** Add the name of the umbrella project to `parent_projects`.
- Example Front Matter:
  ```markdown
  ---
  layout: project
  title: Project Title
  status: Active
  parent_projects:
    - Overarching Thrust Name
  people:
    - Your Name
  sponsors:
    - funding_id
  ---
  Project description goes here...
  ```

### 3. Publications
To add a new publication:
- Navigate to `_publications/`.
- Create a new Markdown file (e.g., `lastname_year_shortname.md`).
- Each publication gets its own detail page where people can view the full abstract and information.
- Example Front Matter:
  ```markdown
  ---
  layout: publication
  title: "Your Paper Title"
  pub_id: "lastname2026shortname"
  date: 2026-04-01
  venue: Conference or Journal Name
  venue_type: Conference  # or "Journal"
  authors:
    - John Davis
    - Gage Hills
    - External Collaborator
  link: "https://example.com/paper"
  projects:
    - project_id_here
  funding:
    - funding_id_here
  awards:
    - award_id_here
  bibtex: |
    @inproceedings{lastname2026shortname,
      title={Your Paper Title},
      author={Davis, John and Hills, Gage},
      booktitle={Conference Name},
      year={2026}
    }
  citation: "John Davis and Gage Hills, 'Your Paper Title', Conference Name, 2026."
  ---
  Your abstract and additional details go here...
  ```
- **Note:** Use list format for `funding` and `awards` even if there's just one item.

### 4. Awards & Recognition
To add an award:
- Navigate to `_awards/`.
- Create a new Markdown file (e.g., `best-paper-2026.md`).
- Each award gets its own detail page and will list publications that received it.
- Example Front Matter:
  ```markdown
  ---
  layout: award
  award_id: best_paper_2026
  title: "Best Paper Award"
  year: 2026
  category: "Example Conference"
  ---
  Award description and details here...
  ```
- To link a publication to an award, add the `award_id` to the publication's `awards` field.

### 5. Assets (Images/PDFs)
- Place all profile pictures in `assets/images/`.
- Ensure filenames match what you write in your Markdown file's `image:` field.

## Advanced Customization
The look and feel of the site is controlled by **SCSS Variables**.
- To change colors or fonts, edit `_sass/_variables.scss`. No other CSS files should be touched for basic re-skinning.
