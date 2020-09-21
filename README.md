# cultfit-clone-backend-design
System design document for cultfit backend

## Intro
I have created this project as my side project. I am a full-stack developer with proficiency in front-end app development. I wanted to enhance my back-end skills, so, I picked up this project. I want to use this project to practice skills like system design. The idea is to follow the below mentioned workflow: 
* Finalize scope/requirements => Identify Entities => Identify attributes and behavior of entities => Identify the relationship between requirements => Identify the APIs requirements => Design APIs
  
## Requirements
  ### Functional
   1. User should be able to register as a **trainee**.
   2. User should be able to register as a **trainer**.
   3. User should be able to login.
   4. Trainer should be able to create a workout seesion.
   5. Trainee should be able to see all the upcoming sessions.
   6. Trainee should be able to register for a particular session.
   7. Trainee should be able to join the session.
      * If the session is not yet started, user will wait in waiting room.
      * If the session has started, user will join the session directly.
   8. Trainer should be able to cancel/reschedule/start the session.
   9. Once the user is in the session, user's energy ratings should get recorded in back-end.
   10. Based on energy ratings, display the rank of the user
   11. Trainers should be able to end session.
   12. View session results (ranking/calories consumed/per minute energy rating).
   13. Trainee should be able to submit feedback for the session.
   14. Trainee should be able to see past history of the workouts.
    
  ### Non-functional
   1. Scalability => There could be thousands of users in a session. 
                     System should be able to handle those users, record their activities and show live rankings.
   2. Performance => Optimize the APIs so that the system is performant.
   3. Security => Implement proper authentiation and authorization.
   4. API documentation => Prepare proper API specification document using Swagger.
   
## Entities and their attributes and behavior
Entities are generally the nouns in our requirements. Behavior is generally the verbs or the actions that the user can take.

|Entity|Attributes|Behaviors|
|------|----------|---------|
|Trainee|full name, email, mobile, password| register, login, view workouts, book workout, join workout, leave workout, rate workout, record energy during workout, view workout history|
|Trainer|full name, email, mobile, isTrainer| register, login, create workout, cancel workout, reschedule workout, start workout, stop workout, view workout history|
|Workout Types| type(ENUM)|-|
|Workout Schedule|workout type (ENUM), coachId, start date & time, duration, description, workout state(ENUM)|-|
|Workout Registration|workoutId, userId|-|
|Energy Tracker|userId, workoutId, time, energy|-|
|Session Result|userId, workoutId, user rank, calories burned, activity duration|-|

TODO: In session result, decide if/how we want to show per minute stats
  
  
  

