## Example slide

this is an example

<div>
<section data-state="head" data-menu-title="Swarming Example">
    <h2>
        Formation of Traffic Jams
    </h2>
    <div class="container">
        <div class="col">
            <br/>
            <ul>
                <li>We have a finite number of cars</li>
                <li>Clearly they do not make perfect decisions otherwise we wouldn't see a jam</li>
                <li>Can we come up with simple rules to explain the jams forming and general behaviour</li>
            </ul>
        </div>
        <div class="col">
            <div class="stretch">
                <iframe width="700" height="400" data-src="https://www.youtube.com/embed/ZNLIoolCeKI"></iframe>
            </div>
        </div>
    </div>
</section>

<section data-state="head" data-menu-title="Swarming Example">
    <h2>
        Synchronisation of Fireflies
    </h2>
    <div class="container">
        <div class="col">
            <br/>
            <br/>
            <br/>
            <ul>
                <li>Not only are we interested in fluid-like flows, we are interested in <b style="color: #1F77B4;">synchronisation</b></li>
                <li>These are fireflies, they start of flashing at random times</li>
                <li>Slowly they "nudge" each other to synchronise up their flashes</li>
            </ul>
        </div>
        <div class="col">
            <div class="stretch">
                <video data-autoplay loop="true" src="conference/fireflies.mp4" width="100%"></video>
            </div>
        </div>
    </div>
</section>

<section data-auto-animate data-state="head" data-menu-title="How we model">
    <h2>Generalised model of interacting agents</h2>
    <p>Cars/Fish/Whatever are $N$ agents with positions $X_n\in[0,2\pi]$ for $n=1,\dots,N$</p>
    <div data-id="sde">
        $$
        \mathrm{d}X_n = \frac{1}{N}\left[\sum_{m=1}^N f(X_m-X_n)\right] \mathrm{d}t + \frac{\sqrt{2D}}{N}\left[\sum_{m=1}^N g(X_m-X_n)\right]^{1/\beta}\mathrm{d}W_n
        $$
    </div>
</section>

<section data-auto-animate data-state="head" data-menu-title="Macroscopic to Mesoscopic">
    <h2>From small scale to large scale</h2>
    <div data-id="sde">
        $$
        \mathrm{d}X_n = \frac{1}{N}\left[\sum_{m=1}^N f(X_m-X_n)\right] \mathrm{d}t + \frac{\sqrt{2D}}{N}\left[\sum_{m=1}^N g(X_m-X_n)\right]^{1/\beta}\mathrm{d}W_n
        $$
    </div>
    <p>
    Introduce a concept of density of particles:
    $$
    \varrho(x,t) = \frac{1}{N}\sum_{n=1}^N \delta_{X_n(t)}(x)
    $$
</section>

<section data-auto-animate data-state="head" data-menu-title="Swarming Example">
    <h2>Particle Density</h2>
    <p>We want a nicer (smoother) way of representing the density</p>
    <div class="container">
        <div class="col">
            <p style="color: #FF8616;">
                $$
                \int_A F(x) \varrho(x,t) \mathrm{d}{x}
                $$
            </p>
            <div class="stretch">
                <img data-src="aims/media/micro.png" style="width:360px;"/>
            </div>
            
        </div>
        <div class="col">
            <div class="fragment">
            <p style="color: #1F77B4;">
                $$
                \int_A F(x) \rho(x,t) \mathrm{d}{x}
                $$
            </p>

            <div class="stretch">
                <img data-src="aims/media/macro.png" style="width:360px;"/>
            </div>
            </div>
        </div>
    </div>
</section>

<section data-auto-animate data-state="head" data-menu-title="Swarming Example">
    <h2>Particle Density</h2>
    <p>We want a nicer (smoother) way of representing the density</p>
    <div class="container">
        <div class="col">
            <p style="color: #FF8616;">
                $$
                \int_A F(x) \varrho(x,t) \mathrm{d}{x}
                $$
            </p>
            <div class="stretch">
                <img data-src="aims/media/meso.png" style="width:360px;"/>
            </div>
            
        </div>
        <div class="col">
            <div>
            <p style="color: #1F77B4;">
                $$
                \int_A F(x) \rho(x,t) \mathrm{d}{x}
                $$
            </p>

            <div class="stretch">
                <img data-src="aims/media/macro.png" style="width:360px;"/>
            </div>
            </div>
        </div>
    </div>
</section>

<section data-state="head" data-menu-title="Macroscopic to Mesoscopic">
    <h2>Particle Density</h2>
    <div data-id="spde", style="color: #FF8616;">
    $$
    \rho_t + \underbrace{\frac{\partial}{\partial x}\left(\rho(f\ast\rho)\right)}_{\text{advection}} - \underbrace{D\frac{\partial^2}{\partial x^2}\left(\rho\left(g\ast\rho\right)^{2/\beta}\right)}_{\text{diffusion}} + \underbrace{\sqrt{\frac{2D}{N}}\frac{\partial}{\partial x}\left((g\ast\rho)^{1/\beta}\rho^{\frac{1}{2}}\eta\right)}_{\text{noise}} = 0
    $$
    </div>

    <!--<p>
        $$
        (f\ast\rho)(x,t) = \int_{-\pi}^{\pi} f(y-x)\rho(y,t) \mathrm{d}y, \quad \langle \eta(x,t)\eta(y,s) \rangle = \delta(x-y)\delta(t-s)
        $$
    </p>-->
    <div class="fragment">
    <p>
        The case where $g(x)=1$ and $\beta=1$, has been studied before (Dean 1996). 
    </p>
    <p>
        $$
        \mathrm{d}X_n = \frac{1}{N}\sum_{m=1}^N f(X_m-X_n) \mathrm{d}t + \frac{\sqrt{2D}}{N}\sum_{m=1}^N g(X_m-X_n)\mathrm{d}W_n
        $$
    </p>
    </div>
</section>
</div>