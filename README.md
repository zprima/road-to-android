# Road to Android

## Projects
  
- [Support All Screen Sizes in Jetpack Compose](https://github.com/zprima/compose-adaptive)
- sorting vizualizer
- matrix character downfall animation
- solar system (animated)
- ToDo app
- webpage parser
- flowr spot mobile (full)
- clock (digital & analog)
- alarm (background trigger)
- weather app
- pokemon list app
  - https://pokeapi.co/docs/v2#pokemon
- trips app
- calendar app (to show work free days)
   
## Links
- Android UI Layer explained: https://youtu.be/p9VR8KbmzEE

<img src="vm_as_state_holder.png" height="200px" />

- [TheAndroidShow](https://www.youtube.com/hashtag/theandroidshow)

## Project Structure
[Guide to app arhitecture](https://developer.android.com/jetpack/guide)

- ui
  - theme
  - navigation
  - screens
    - viewmodel
    - uistate
  - components
- domain (optional)
  - usecase (verb in present tense + noun/what (optional) + UseCase)
  - repository (interfaces - definitions)
- data
  - model  
  - repository (implementations of interfaces) (type of data + Repository)
  - data sources (type of data + type of source + DataSource) (NewsLocalDataSource, NewsRemoteDataSource)
    - local
        - entity
        - dao
        - database
    - remote
        - dao
        - retrofit
  - work managers* (if any)
  - mappers (from db/remote model to model we want to use in our app/domain)
- di
  - modules (network, app, database, ...)
- util
  - constants
  - converters (date, uuid, ...)
