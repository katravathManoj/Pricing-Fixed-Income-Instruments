This project is designed to evaluate and **price fixed-income instruments (bonds) and derivative instruments (swaps)** under varying interest rate conditions. The sensitivity analysis through PV01 and DV01 is especially valuable for managing interest rate risk in these financial products, which is critical in fields like risk management, treasury operations, and fixed-income portfolio management.


The project detailed in the code encompasses several components that collectively handle yield curve construction, shock analysis, cashflow generation, and valuation for a financial instrument. Here is a summary of the main parts:

1. **Date Calculation and Curve Interpolation**: The project starts by calculating dates based on tenors (e.g., weeks, months, years) using the `DCC_Handler` function. This function also manages holidays and weekends, adjusting dates accordingly. A curve constructor function (`Curve_Constructor`) is implemented to interpolate rates linearly or cubically across calculated index positions.

2. **Curve Shocks**: The `Curve_Shock_Handler` function applies up or down shocks to interest rates by specified basis points, allowing stress testing of the yield curve. This shock-adjusted curve is used to assess rate sensitivity in the financial instrument.

3. **Cashflow Generation**: 
   - **Floating Rate Cashflows**: The project calculates floating rate cashflows based on the compounded SOFR (Secured Overnight Financing Rate) rates, incorporating a daily rate compounding function.
   - **Fixed Rate Cashflows**: Separate cashflows are generated for the fixed leg, using a specified fixed interest rate.
   - **Payment Schedules**: Cashflow schedules are created quarterly or semi-annually, adjusting dates for holidays and weekends.

4. **Net Present Value (NPV) and DV01 Calculations**: NPV is calculated for both fixed and floating legs using discount factors derived from the zero-coupon curve. DV01, a sensitivity measure, is calculated by adjusting rates and recalculating the NPV to assess the effect of a small rate shift.

5. **Rate Interpolation and Plotting**: The interpolated SOFR, zero, and basis curves are generated for various maturities and plotted, demonstrating the continuous structure of interest rates over time.

6. **Cashflow and Discount Factor Outputs**: Cashflows, discount factors, and shock-adjusted NPVs are generated for both legs of the swap, with the net value indicating the instrument's valuation under different scenarios.

This project primarily showcases yield curve construction, shock testing, and cashflow modeling for evaluating swaps or fixed-income securities.
