# Angular Project EP2 : AUTH(forChild) & SHARED COMPONENT

## Authentication Component [ forChild() ]
- 'app.routing.ts'
```bash
    { path: AppURL.Authen, loadChildren: () => import('./authentication/authentication.module').then(m => m.AuthenticationModule) }
]
```
- Create folder 'authentication'
- Create Module 'authentication.modules'
- Create folder 'authentication/components'
- Craete Components 
  ```bash
  $ ng g c dashboard
  ```
- Create file 'authentication.url.ts'
  ```bash
  export const AuthURL = {
      Dashboard: 'dashboard'
  }
  ```
- Create file 'authentication.routing.ts'
  ```bash
  import { AuthURL } from './authentication.url'
  ```
  ```bash
  const RouteLists: Routes = [
      { path: AuthURL.Dashboard, component: DashboardComponent }
  ];
  ```
  ```bash
  export const AuthenticaionRouting = RouterModule.forChild(RouteLists);
  ```
- Import to 'authentication.modules.ts'
  ```bash
  imports: [
    AuthenticaionRouting,
  ] 
  ```

## Shared Component
- Create folder 'shared'
- Create folder 'shared/component'
- Create Component 'auth-navbar', 'auth-sidebar' and 'auth-content'
  ```bash
  $ ng g c auth-navbar
  $ ng g c auth-navbar
  $ ng g c auth-navbar
  ```
- Add into 'app.modules.ts'
  ```bash
  imports: [
    SharedModule
  ]
  ```
- Add into 'shared.modules.ts'
  ```bash
  exports: [
    AuthNavbarComponent,
    AuthSidebarComponent,
    AuthContentComponent
  ]
  ```
- Add into part for use
  ```bash
  imports: [
    SharedModule
  ]
  ```
- tag on '@Component' Selecter for use etc 
  ```bash
  <auth-navber></auth-navber>

  <!-- USE 'auth-content' -->   |  <!-- etc -->     |   <!-- equal -->
  <auth-navber>                 |  <auth-content>   |   <auth-navber>   
    <ng-content></ngcontern>    |    Hello World    |     Hello World
  </auth-navber>                |  </auth-content>  |   </auth-navber>
  
  ```