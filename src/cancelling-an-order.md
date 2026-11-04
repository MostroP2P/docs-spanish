# ¿Puedo cancelar una orden?

Si creaste una orden y aún no ha sido tomada, puedes cancelarla sin problema. Esto incluye una orden que todavía espera su [depósito anti-abuso](./anti-abuse-bond.md). En la [Mostro App](./mostro-mobile.md), abre tu orden y confirma *¿Cancelar la orden?* con **Sí, cancelar**.

Si la orden ya fue tomada pero la operación aún no empezó —el vendedor no pagó la [hold invoice](./hold-invoice.md) o el comprador no envió su factura—, cualquiera de los dos puede cancelarla directamente, sin el consentimiento del otro.

Una vez que los sats del vendedor están bloqueados, si decides no continuar deberás iniciar una cancelación cooperativa con tu contraparte. En la app, toca **Cancelar operación**; tu contraparte verá **Aceptar cancelación**. Si ambos están de acuerdo, Mostro cancelará la [hold invoice](./hold-invoice.md) pagada por el vendedor, y los sats serán devueltos a este. Esto también funciona mientras hay una disputa abierta, y la cierra.

En caso de que tu contraparte no quiera cancelar, puedes iniciar una [disputa](./disputes.md).
