# Laravel Auth
Inseriamo l'autenticazione fornita da Laravel per gestire le rotte admin di un CMS

## Step 1
1. Creiamo il progetto `composer create-project --prefer-dist laravel/laravel:^7.0 ./`
2. installiamo laravel ui `composer require laravel/ui:^2.4`
3. creiamo lo scaffolding per vue `php artisan ui vue --auth`
    *ricordarsi di far girare **npm** (`npm install` e `npm run dev`)*
4. Creiamo un nuovo **database** tramite phpMyAdmin e inseriamo le credenziali corrette nel file `.env` 
    *se abbiamo già fatto partire l'**artisan serve** lo stoppiamo e lo facciamo ripartire*
5. Avviamo le **migrations**: `php artisan migrate`

## Step 2: Back Office
1. Laravel crea già un **HomeController**, cancelliamolo e creiamo al suo posto un HomeController sotto il **namespace Admin** che gestirà la pagina di atterraggio dopo il login.
`php artisan make:controller Admin/HomeController`
2. definiamo le **rotte** per la parte di backoffice, raggruppandole con namespace, prefisso, middleware auth e name
3. definiamo una rotta `/admin` che porta alla dashboard del backoffice e modifichiamo la **path** della costante HOME nel file `app/Providers/RouteServiceProvider.php`
4. creiamo un **layout** per la parte dashboard nel backoffice
5. creiamo una sottocartella `resources/views/admin/` per gestire tutte le views lato **backoffice**