# Root Causes

Please copy-paste the final answer that you obtained from the AI for each question. The chat interface has a copy button that you can use to copy each message in Markdown format. Please do NOT include images or screenshots.

## Problem 1

**Problem**: The tags are broken up into individual characters on the post view page.

**Question**: What is the underlying issue that causes this problem to occur and from which component (file) of this project does this issue originate?

**Answer**: *The frontend is incorrectly splitting the tags string by each character instead of by commas. This happens in the post creation component, likely in apps/frontend/src/app/components/post-create/post-create.component.ts (or the corresponding file handling form submission). The code currently uses .split('') or similar, which breaks the tag string into individual characters. The fix is to split the tags by commas and trim any whitespace.*


## Problem 2

**Problem**: New tags  are not shown on the home page under "Popular Tags", even after a page refresh.

**Question**: What is the underlying issue that causes this problem to occur and from which component (file) of this project does this issue originate?

**Answer**: *The backend API responsible for returning popular tags does not include newly created tags immediately, or the frontend does not correctly fetch or update the tags list after creating a new post. This originates from the popular tags service or API controller in apps/backend/src/modules/tags/tags.controller.ts (or the relevant service file handling tag retrieval). The fix is to ensure new tags are saved correctly and returned by the API, and the frontend fetches the updated list after a post is created.*

