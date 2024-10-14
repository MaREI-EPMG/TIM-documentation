.. _ss:times_code:

TIMES Model generator
=======================

TIMES (The Integrated MARKAL-EFOM System) is a bottom-up optimization model generator for energy-environment systems analysis at various levels of spatial, temporal, and sectoral resolutions [#Loulou2016a; #Loulou2016]. The TIMES code, written in GAMS and available under an open-source license [#IEA-ETSAP2020a], is developed and maintained by the Energy Technology Systems Analysis Programme (ETSAP)\ [#]_ , a Technology Collaboration Programme (TCP) of the International Energy Agency (IEA), established in 1976. TIMES models can have single or several regions and typically are rich in technology detail, used for medium- to long-term energy system analysis and planning at a regional, national, or global scale.

TIMES is a linear optimization, techno-economic, partial-equilibrium model generator that assumes perfectly competitive markets and perfect foresight. Model variants enable myopic foresight, general equilibrium, stochastic programming, and a variety of multi-objective function options. The standard objective function maximizes the net total surplus (the sum of producers’ and consumers’ surpluses), which, in a perfect market with perfect foresight, equates to maximizing the net present value (NPV) of the whole energy system, maximizing societal welfare. Profits, taxes, and subsidies are internal transfers, i.e., occurring within the economy, that do not change the NPV (albeit taxes and subsidies can be included to influence the optimization). It calculates the energy system specification that minimizes discounted total energy system costs over the model time horizon, which is the sum of investments, fixed and variable costs, fuel import costs, and export revenues for all the modeled processes, less potential salvage values of investments for which the whole lifetime goes beyond the model time horizon.

The user inputs the following to the model generator:

- Reference Energy System (RES): The process-flow architecture of economic sectors and energy flows (commodity) between processes (technology), which consume and produce energy, energy service demands and/or other commodities such as environmental emissions (including greenhouse gasses) and other materials. The base-year energy flows are calibrated to national energy balances.
- Energy service demands: The physical services required by the economy and society for mobility, heat, communications, food, etc., which drive energy demand.
- Energy supply curves: The quantities of primary energy resources (e.g., wind power) or imported commodities (e.g., oil, gas, bio-energy) available at specific cost points for differing quality and quantity of energy commodities.
- Techno-economic parameters of existing and potential future energy technologies: Economic parameters including current and projected future investment and fixed/variable costs and efficiencies of technologies for energy supply (e.g., solar PV panels, transmission and distribution infrastructure, biorefineries, hydrogen production) and energy demand (e.g., electric vehicles, natural gas boilers, carbon capture and storage); technological parameters including transformation efficiency, availability factor, capacity factor, and emissions factor.
- User constraints: Any combination of linear constraints (including fixed, maximum, or minimum bounds on growth, investment, or shares) on technologies or fuels. These are typically used to simulate real-world technology constraints or policy scenarios. A typical user constraint for decarbonization analysis is limiting total annual or cumulative CO\ :sub:`2`\  emissions to model energy system pathways that meet a national decarbonization target.

TIMES outputs the optimal investment and operation level of all energy technologies that meet future energy service demands at the least cost, while respecting user constraints. The model also produces corresponding energy flows, emissions, and marginal prices of energy and emissions flows.

.. [#] https://iea-etsap.org/

.. _ss:system_overview:

Model architecture
----------------------------

.. figure:: figures/TIM_RES.png
   :scale: 60%
   :align: center
   :alt: Simplified representation of reference energy system in TIM

   Simplified representation of reference energy system in TIM

Figure 1 illustrates a simplified Reference Energy System (RES) within the TIMES-Ireland Model (TIM). It delineates the structure and energy flows, encompassing two primary components:

* **Supply-side:** Encompasses energy resources (domestic fossil fuels and renewables), fuel production and conversion technologies (biorefineries, hydrogen production, power plants), and transmission/distribution infrastructure (gas pipelines, power grid).
* **Demand-side:** Covers end-use sectors (transport, residential, etc.) and their corresponding energy service demands (passenger transport, freight, hot water, etc.).

Energy resources, both domestic and imported, are processed and distributed across the country. End-use technologies consume these energy commodities to satisfy the energy service demands of various sectors. Greenhouse gas (GHG) emissions, arising from fossil fuel combustion and industrial processes, are meticulously tracked at the fuel supply, electricity generation, and sectoral consumption levels.

The model's base year is 2018, with all energy flows, emissions, and energy technology stocks calibrated to the 2018 Irish energy balance [SEAI2019].

**Discount Rate:**

The discount rate, signifying the degree to which future values are discounted to the present, is a pivotal parameter in the TIMES objective function.  A *social discount rate* reflects societal preferences regarding present versus future costs and benefits, typically lower than a *financial discount rate* used by firms for investment decisions. The Irish government employs a social discount rate of 4% in this model, aligned with the Social Rate of Time Preference methodology outlined in the Public Spending Code [OCallaghan2018]. This rate is consistent with recommendations by Garcia-Gusano et al. (2016) for a maximum social discount rate of 4-5% in Energy System Optimization Models (ESOMs).

**Technology-Specific Discount Rates:**

Technology-specific discount rates, also known as hurdle rates, are often used in ESOMs to model investment decisions from the individual or industry perspective. They account for market imperfections, financial limitations, and behavioral factors that can hinder the adoption of novel or capital-intensive technologies. These parameters are not incorporated in the core TIM version, as it focuses on long-term energy system pathways from a societal viewpoint. However, model variants can be developed to simulate real-world policy and behavioral impacts, potentially including hurdle rates [Aryanpur2022].

