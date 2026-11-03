# Masterarbeit / AI Robotics Application Board

A lightweight, framework-free application tracker. It works as a local HTML page and can be published directly with GitHub Pages.

The page has two sections: the main application Kanban uses `applications.json`, while **LUH Professors & Projects** uses `luh.json` to track reviewed topics, professor outreach, replies, and follow-ups without mixing them into formal job statistics.

## Open locally

Double-click `index.html`. In local file mode, the page uses its built-in starter snapshot because browsers normally block automatic reading of a neighboring JSON file.

To see changes from `applications.json` locally, click **Import JSON** and choose that file. The page can also export the currently loaded records as a formatted JSON file.

## Add or edit a record

Open `applications.json` in a text editor, copy an existing object, and change its fields. Keep commas between objects and use double quotes around text.

Recommended values:

- `category`: `company`, `applied-research`, or `LUH`
- `status`: `Found`, `Applied`, `Waiting`, `Interview`, `Rejected`, `Offer`, or `Closed`
- `priority`: `High`, `Medium`, or `Low`
- `record_type`: `application` or `networking`

`Rejected`, `Offer`, and `Closed` records appear in the **Closed** Kanban column. Records with `record_type: "networking"` are visible on the board but excluded from the formal application summary.

Dates should use `YYYY-MM-DD`, for example `2026-11-03`. `technical_focus` is a JSON list, for example:

```json
"technical_focus": ["VLA", "Robot Manipulation", "Embodied AI"]
```

## Publish with GitHub Pages

1. Create a GitHub repository and upload all three files from this folder.
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select the branch containing the files (usually `main`) and the root folder, then save.

On GitHub Pages, `index.html` automatically loads `applications.json`, so editing the JSON in the repository updates the board after deployment.

## Data model

Each record supports:

`organization`, `city`, `title`, `category`, `technical_focus`, `status`, `applied_date`, `last_contact`, `next_action`, `application_link`, `contact_person`, `contact_channel`, `notes`, `priority`, and `record_type`.
