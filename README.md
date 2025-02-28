# FlexHeaven
# Flowchart
```mermaid
flowchart TD
    Start([User Opens App]) --> Auth{Authenticated?}
    
    %% Authentication Flow
    Auth -->|No| Login[Login Screen]
    Login -->|Register| Register[Registration Form]
    Register -->|Success| Auth
    Login -->|Submit| Validate{Validate Credentials}
    Validate -->|Invalid| Login
    Validate -->|Valid| HomeScreen
    
    %% Main Navigation
    Auth -->|Yes| HomeScreen[Home Screen]
    HomeScreen --> Categories[Browse Categories]
    HomeScreen --> Search[Search Content]
    HomeScreen --> MyList[My List]
    HomeScreen --> Profile[User Profile]
    
    %% Category & Browsing Flow
    Categories --> Movies[Movies]
    Categories --> Series[TV Series]
    Categories --> New[New Releases]
    Categories --> Trending[Trending]
    
    Movies --> MovieDetails[Movie Details]
    Series --> SeriesDetails[Series Details]
    SeriesDetails --> Episodes[Episode Selection]
    
    %% Search Flow
    Search --> Results[Search Results]
    Results --> ContentDetails[Content Details]
    
    %% Content Interaction
    MovieDetails --> Play[Play Movie]
    Episodes --> PlayEpisode[Play Episode]
    
    MovieDetails --> AddToList[Add to My List]
    SeriesDetails --> AddToList
    
    %% User Profile
    Profile --> AccountSettings[Account Settings]
    Profile --> Subscription[Subscription Management]
    Profile --> WatchHistory[Watch History]
    
    %% Playback
    Play --> Stream{Start Stream}
    PlayEpisode --> Stream
    Stream -->|Buffer| Loading[Loading/Buffering]
    Loading --> Playback[Content Playback]
    
    %% Playback Controls
    Playback --> Controls[Playback Controls]
    Controls --> Pause[Pause/Resume]
    Controls --> Seek[Seek Forward/Backward]
    Controls --> Quality[Quality Settings]
    Controls --> Exit[Exit Playback]
    
    %% Exit Flows
    Exit --> ResumePoint[Save Resume Point]
    ResumePoint --> HomeScreen
    
    %% Color Classes
    classDef authColor fill:#E57373,stroke:#333,stroke-width:1px,color:#000
    classDef navColor fill:#81C784,stroke:#333,stroke-width:1px,color:#000
    classDef contentColor fill:#64B5F6,stroke:#333,stroke-width:1px,color:#000
    classDef userColor fill:#BA68C8,stroke:#333,stroke-width:1px,color:#000
    classDef playbackColor fill:#FFD54F,stroke:#333,stroke-width:1px,color:#000
    classDef decisionColor fill:#FF7043,stroke:#333,stroke-width:1px,color:#fff
    classDef actionColor fill:#4DB6AC,stroke:#333,stroke-width:1px,color:#000
    classDef highlightColor fill:#F06292,stroke:#333,stroke-width:2px,color:#fff
    
    %% Apply Classes
    class Start,Exit highlightColor
    class Auth,Validate,Stream decisionColor
    class Login,Register,ResumePoint authColor
    class HomeScreen,Categories,Search,MyList,Profile navColor
    class Movies,Series,New,Trending,MovieDetails,SeriesDetails,Episodes,Results,ContentDetails contentColor
    class AccountSettings,Subscription,WatchHistory userColor
    class Play,PlayEpisode,Loading,Playback,Controls,Pause,Seek,Quality,Exit playbackColor
    class AddToList actionColor

```

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 16.2.1.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.


## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests 

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

