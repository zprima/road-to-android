# Road to Android

## Projects
  
- [Support All Screen Sizes in Jetpack Compose](https://github.com/zprima/compose-adaptive)
- [Sorting vizualizer](https://github.com/zprima/compose-sorting-visualizer)
- [matrix character downfall animation](https://github.com/zprima/compose-matrix)
- [solar system (animated)](https://github.com/zprima/compose-solar-system)
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

- ui (outer layer - it includes domain and data)
  - theme
  - navigation
  - screens
    - viewmodel
    - uistate
  - components
- domain (its the most inner layer in the clean arhitecture. OPTIONAL - depends on app size. For small apps its just not worth it.)
  - usecase (verb in present tense + noun/what (optional) + UseCase)
  - repository (interfaces only)
  - model
- data (mid layer - it includes domain) 
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
  - mappers (from db/remote model to domain model we want to use in our app/domain)
- di
  - modules (network, app, database, ...)
- util
  - constants
  - converters (date, uuid, ...)

In case DOMAIN module exists, the following is set:   
UI module interacts with the DOMAIN module, does not interact with DATA module directly.   
DATA module implements DOMAIN interfaces, does not interact with UI module directly.   

Wrote a post about it: [Android Jetpack Compose: Clean Arhitecture — 2022](https://anmagpie.medium.com/android-jetpack-compose-clean-arhitecture-2022-8ea280c91fd5)
   
## Resource class for utils:
<pre>
  sealed class Resource<T>(val data: T? = null, val error: String? = null){   
     class Success<T>(data: T?): Resource<T>(data)   
     class Error<T>(error: String?, data: T? = null): Resource<T>(data, error)   
     class Loading<T>(val isLoading: Boolean = true): Resource<T>(null)
  }
</pre>

