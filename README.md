## Proposed Change
Replace `create-react-app` and `MERN` stack with `Next.js`

[Example project in new proposed project structure](https://github.com/ChristianMLand/authors_with_auth) 
## Considerations (Pros and Cons)
- Amount of work to modify track to match this new structure (detailed below)
- The React devs themselves helped work on the newest version of Next.js (v13) and support it as the recommended way to use react on their official documentation.
- Need to decide on Next.js 12 or Next.js 13 (officially suggested is installing latest but using 12 project structure)
- Next.js 13 is currently in beta and has a different project structure compared to Next.js 12
    - the new project structure and features are all optional and non-breaking for now, so projects can still be structured like 12, but take advantage of the new features in 13, but that might change with future versions
    - By knowingly sticking with the Next.js 12 structure, even though they are trending towards the new 13 structure means another rewrite would likely need to happen eventually. 
    - **Note** the changes between 12 and 13 are not nearly as significant as the differences between the current stack structure and Next.js, so it would be a much more minor update.
- Next.js is extremely popular in the industry and a much more modern approach to full stack with react 
    - it can technically still be considered a MERN stack, since still using react, express, node, and mongoDB as express is used internally by next.js
## Chapters and Assignments That Need Modification
- React Unit (15 / 56) <details>
    <summary>Expand</summary>

    - Intro to React ( 3 / 8 )
        - create-react-app **`Replaced`**
            - replaced with `create-next-app`
        * folder structure **`Replaced`**
            - replaced with next.js folder structure
        - using JSX **`Modified`**
            - should show functional components in the example instead of class components, nothing Next.js specific
    - Class Components ( 6 / 12 )
        - entire section should be probably moved / reduced to be more optional
        - class components **`Modified`**
            - really just the video, other content is still valid for Next.js
        - props **`Modified`**
            - really just the video, other content is still valid for Next.js
        - children **`Modified`**
            - material is the same, but reference to App.js should be changed
        - synthetic events **`Modified`**
            - material is the same, but reference to App.js should be changed
        - state **`Modified`**
            - just the video
        - react blocks **assignment** **`Modified`**
            - just need to adjust given starter code slightly to match next.js
    - Functional Components ( 3 / 22 ) 
        - Context API **`Modified`**
            - concepts are the same, but the code snippet needs to be adjusted slightly
        - Context with state **`Modified`**
            - concepts are the same, but code snippet and wording needs to be slightly adjusted to match next.js structure
        - navbar context **assignment** **`Modified`**
            - starter code and wording needs to be adjusted slightly to match next.js structure
    - APIs ( 0 / 8 )
        - no necessary changes 
        - I think we should introduce async/await much sooner in the stack, and I think this section is the best place for it
    - React Routing *should be renamed to Next.js Routing ( 3 / 6 )
        - react router **`Replaced`**
            - replaced with content on next.js routing
        - useParams **`Replaced`**
            - replaced with  next.js `useRouter` hook
        - useNavigate **`Removed`**
            - `useRouter` hook handles both params, and navigation

</details>

- Express Unit  ( 3 / 8 )<details>
    <summary>Expand</summary>

    - *Should be renamed to Next.js APIs
    - Express + Nodemon **`Removed`**
    - Routing **`Replaced`**
        - should be replaced with discussion on Next.js pages/api folder
    - folder structure **`Removed`**
</details>

- MongoDB Unit ( 1 / 12 ) <details>
    <summary>Expand</summary>

    - MongoDB ( 0 / 7 )
        - no changes necessary
    - Mongoose ( 1 / 5 ) 
        - Express + mongoose **`Modified`**
            - The code is mostly the same, but should be in relation to next.js now instead of express
        - might be worth covering virtuals, statics, and pre/post middleware here so we can introduce login/reg in fullstack
</details>

- Full Stack MERN unit ( 9 / 21 ) <details>
    <summary>Expand</summary>

    - *should be renamed to Full Stack Next.js  
    - Full Stack MERN *should be renamed to Full Stack Next.js ( 7 / 11 )
        - Introduction **`Modified`**
            - should be modified to match next.js structure
        - Setting up MERN **`Removed`**
        - Hello World **`Modified`**
            - content can be kept similar, but just with next.js structure, video needs to be redone as well
        - Create (Part I) **`Modified`**
            - videos need to be either removed or redone, mongoose stuff can stay the same, controller should be update to match next.js api structure, server and route code should be removed
        - Create (Part II) **`Modified`**
            - video needs to either be removed or redone, rest of the content is almost identical however, just needing to change the port from `localhost:8000` to `localhost:3000`
        - List and Detail **`Modified`**
            - react stuff can stay mostly the same, server stuff should be adjusted to match next.js structure
        - Update and Delete**`Modified`**
            - react stuff can stay mostly the same, server stuff should be adjusted to match next.js structure
    - Advanced MERN *should be renamed to Advanced Next.js ( 2 / 10 )
        - Presentational vs Container  **`Removed`**
            - this difference should be made back in the React unit when first discussing next.js pages
        - Material-UI **`Modified`**
            - setup needs some minor additions, but the rest of the contents the same  
            - would recommend replacing this with tailwind as it is natively bundled with next.js now (if opted in)
        - Additional (optional) chapters that don't exist should be made on topics such as Server Side rendering, and SWR
        - Auth could be moved here as well into a couple chapters, as it can be done **much** simpler now with `iron-session`
            - `iron-session` still relies on the same concepts as JWTs so they are still using cookies on every request to have a stateless session, just done in a much simpler to use way
</details>

- Sockets ( 3 / 5 ) <details>
    <summary>Expand</summary>

    - Sockets on the server **`Modified`**
        - code needs to be adjusted to match next.js structure, some other minor changes as well
    - Sockets on the Client **`Modified`**
        - code is similar but needs to be adjusted to match next.js structure
    - creating the handshake **assignment** **`Modified`**
        - only need to change requirements checklist, rest is fine
</details>

- MERN Auth ( 7 / 10 ) <details>
    <summary>Expand</summary>

    - *instead of being its own unit, should be simplified and put in with Advanced Next.js 
    - User Model **`Modified`**
        - mostly the same, but code should be refactored, and login validation static method should be added
    - Registration **`Modified`**
        - mostly the same, but should be in format of a Next.js API
    - Environment Variables **`Modified`**
        - mostly the same, but don't require dotenv as Next.js has builtin .env support
    - JSON Web Tokens **`Replaced`**
        - should be replaced with a chapter on `iron-Session`
    - Cookies **`Modified`**
        - can be kept similar, but just change to match `iron-session`
    - async/await 
        - should be moved to much earlier in the stack, probably in the react apis unit, no other changes needed though
    - Login/Logout **`Replaced`**
        - needs a rewrite to match iron-sesion structure, and move login validations to static method in model
    - Authorization and Middleware **`Replaced`**
        - should be replaced to match `iron-session`/next.js structure)
</details>

- MERN Deployment ( 4 / 4 ) <details>
    <summary>Expand</summary>

    - *Should be changed to Next.js Deployment 
    - needs to be redone to match `next.js` project structure. overall process is similar when deploying with AWS though
    - Should add optional chapter for deployment with vercel (which is much simpler and only requires a couple button clicks)
</details>

## Conclusion
### **TOTAL** ( 42 / 116 ) chapters impacted
- At least 5 chapters can be completely removed without any loss of content
- Only about 8 chapters need a complete re-write
- About 30 chapters need some form of modification (most are extremely minor changes in wording while content remains the same)
- Around 6 videos need to be redone ( not including solution videos )
- and only 3 assignments need any form of modification (very minor changes)
- Depending on how deep we want to explore Next.js, anywhere from 0-7 new chapters could be added
- Roughly 35% of the stack needs to be modified in some way, however many of these changes are minor
- Making these changes will better prepare students for working with React in the industry
- use es6 syntax consistently for front end and backend rather than having it only for react and needing to use things like `require` for the backend will hopefully prevent confusion
- project structure and setup is greatly simplified and consistent for frontend and backend
- could have Auth be a requirement before the exam now as well to better match our other stacks
- deployment is made incredibly simpler if using vercel
