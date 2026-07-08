---
title: page 1
deprecated: false
hidden: false
metadata:
  robots: index
---
In SAPIENT, while [configuring the tracking webhook](https://docs.intersoftsapient.net/docs/create-tracking-webhook), You can choose to receive <Glossary>all tracking events</Glossary> or tracking <Glossary>milestones</Glossary> only.

* If you select to receive milestones only, the system only pushes the tracking when a new milestone is triggered.
* If you select to receive full tracking events, then the system pushes the tracking every time it receives a new tracking event from the carrier, regardless of whether the tracking event triggers a new milestone or not.

***

## INTERSOFT tracking events

The following section displays a comprehensive structure of the milestones, event codes, and events that occur throughout the shipping journey of a shipment.

<Accordion title="Tracking Events and Milestones" icon="fa-duotone fa-solid fa-display-chart-up">
  <HTMLBlock>{`
                <table>
                <tr>
                <th style="background-color: #778899;">Milestone Name</th>
                <th style="background-color: #778899;">Milestone Order</th>
                <th style="background-color: #778899;">Tracking Event Code</th>
                <th style="background-color: #778899;">Tracking Event Name</th>
                </tr>
                <tr>
                <td rowspan="7"><strong>It’s on its Way</strong></td>
                <td rowspan="7">1</td>
                <td>PSRE</td>
                <td>The shipment has been received into the carrier network for processing.</td>
                </tr>
                <tr>
                <td>PSAN</td>
                <td>Shipment details have been received and the parcel is awaiting collection or handover.</td>
                </tr>
                <tr>
                <td>PSCO</td>
                <td>The shipment has been successfully collected by the carrier.</td>
                </tr>
                <tr>
                <td>PSDE</td>
                <td>he shipment has been dispatched and is moving through the carrier network.</td>
                </tr>
             <tr>
                <td>CAMD</td>
                <td>The scheduled collection has been updated or amended after booking.</td>
                </tr>
             <tr>
                <td>CSBK</td>
                <td>The collection request has been successfully booked and confirmed.</td>
                </tr>
             <tr>
                <td>PSCS</td>
                <td>The shipment has been collected from a designated safe place as instructed.</td>
                </tr>
                <tr>
                <td rowspan="5"><strong>In Transit</strong></td>
                <td rowspan="5">2</td>
                <td>PINT</td>
                <td>The shipment is in transit and progressing towards the delivery destination.</td>
                </tr>
                <tr>
                <td>PPID</td>
                <td>The shipment has been processed at a carrier depot facility.</td>
                </tr>
                <tr>
                <td>PRID</td>
                <td>The shipment has been received at a depot and is ready for sorting.</td>
                </tr>
                <tr>
                <td>PSDD</td>
                <td>The shipment has departed from a depot and is en route to the next location.</td>
                </tr>
                <tr>
                <td>IOWS</td>
                <td>The shipment exceeds size or weight limits and may require special handling.</td>
                </tr>
                <tr>
                <td rowspan="3"><strong>In Customs</strong></td>
                <td rowspan="3">3</td>
                <td>BCUI</td>
                <td> The shipment is undergoing customs inspection by authorities.</td>
                </tr>
                <tr>
                <td>BHBC</td>
                <td>The shipment is being held by customs pending further review or clearance.</td>
                </tr>
                <tr>
                <td>BRBC</td>
                <td>The shipment has been released by customs and will continue transit.</td>
                </tr>
                <tr>
                <td rowspan="1"><strong>Out for Delivery</strong></td>
                <td>4</td>
                <td>POFD</td>
                <td>The shipment is out for delivery and expected to reach the recipient.</td>
                </tr>
                <tr>
                <td rowspan="8"><strong>Delivery Attempt Failed</strong></td>
                <td rowspan="8">5</td>
                <td>FDAF</td>
                <td>A delivery attempt was made but was unsuccessful.</td>
                </tr>
                <tr>
                <td>FNCO</td>
                <td>The shipment was not collected as scheduled.</td>
                </tr>
                <tr>
                <td>FCAR</td>
                <td>Delivery was attempted but no answer; a notification card has been left.</td>
                </tr>
                <tr>
                <td>FANK</td>
                <td>Delivery failed due to an unknown or incorrect address.</td>
                </tr>
                <tr>
                <td>FRNK</td>
                <td>Delivery could not be completed as the recipient is not known at the address.</td>
                </tr>
                <tr>
                <td>FRAA</td>
                <td>Delivery was refused at the destination address.</td>
                </tr>
                <tr>
                <td>FINA</td>
                <td>Delivery failed due to incomplete or missing address details.</td>
                </tr>
                <tr>
                <td>FUTA</td>
                <td>Delivery could not be completed as access to the delivery location was not possible.
</td>
                </tr>
                <tr>
                <td rowspan="1"><strong>Part Delivered</strong></td>
                <td>6</td>
                <td>DPAR</td>
                <td>The shipment has been partially delivered (only part of the consignment delivered).</td>
                </tr>
                <tr>
                <td rowspan="1"><strong>Ready for Collection</strong></td>
                <td>7</td>
                <td>DRFC</td>
                <td>Ready for Collection</td>
                </tr>
                <tr>
                <td rowspan="8"><strong>Delivered</strong></td>
                <td rowspan="8">8</td>
                <td>DELV</td>
                <td>The shipment has been successfully delivered to the intended recipient.</td>
                </tr>
                <tr>
                <td>DTSP</td>
                <td>The shipment has been delivered to a designated safe place.</td>
                </tr>
                <tr>
                <td>DPOB</td>
                <td>The shipment has been delivered to a PO Box.</td>
                </tr>
                <tr>
                <td>DDMG</td>
                <td>The shipment has been delivered but with reported damage.</td>
                </tr>
                <tr>
                <td>DTNB</td>
                <td>The shipment has been delivered to a neighbour without signature confirmation.</td>
                </tr>
                <tr>
                <td>DTNS</td>
                <td>The shipment has been delivered to a neighbour with signature confirmation.</td>
                </tr>
                <tr>
                <td>DNSV</td>
                <td>The shipment has been delivered to a neighbour with ID verification and signature.</td>
                </tr>
                <tr>
                <td>DNSO</td>
                <td>The shipment has been delivered to a neighbour with signature and age verification of over 25.</td>
                </tr>
                <tr>
                <td rowspan="1"><strong>Collected</strong></td>
                <td>9</td>
                <td>DRCO</td>
                <td>The shipment has been collected directly by the recipient from the carrier location.</td>
                </tr>
                <tr>
                <td rowspan="7"><strong>Undeliverable</strong></td>
                <td rowspan="7">10</td>
                <td>RTNS</td>
                <td> The shipment is being returned to the sender.</td>
                </tr>
                <tr>
                <td>RUND</td>
                <td>The shipment is undeliverable and is being returned to the sender.</td>
                </tr>
                <tr>
                <td>RNCO</td>
                <td>The shipment was not collected and is being returned to the sender.</td>
                </tr>
                <tr>
                <td>UDTS</td>
                <td>The returned shipment has been delivered back to the sender.</td>
                </tr>
                <tr>
                <td>IDES</td>
                <td>The shipment has been lost or destroyed while in transit.</td>
                </tr>
                <tr>
                <td>ICAN</td>
                <td>The shipment or collection request has been cancelled.</td>
                </tr>
                <tr>
                <td>FUDS</td>
                <td>The shipment is undeliverable and has been destroyed.</td>
                </tr>

                <tr>
                <td rowspan="4"><strong>Transit Delay</strong></td>
                <td rowspan="4">Null</td>
                <td>IDIP</td>
                <td>The shipment processing has been delayed within the carrier network.</td>
                </tr>
                <tr>
                <td>IFME</td>
                <td>Delivery is impacted due to an exceptional event (e.g. weather, disruption).</td>
                </tr>
                <tr>
                <td>ISMI</td>
                <td>The shipment has been misrouted and is being redirected to the correct route.</td>
                </tr>
                <tr>
                <td>PRET</td>
                <td> The shipment is being held or retained by the carrier temporarily.</td>
                </tr>
                <tr>
                <td rowspan="18"><strong>N/A</strong></td>
                <td rowspan="18">Null</td>
                <td>ICLR</td>
                <td>Customs clearance has been completed successfully.</td>
                </tr>
                <tr>
                <td>IARR</td>
                <td>The shipment has arrived at a processing or distribution facility.</td>
                </tr>
                <tr>
                <td>IRCO</td>
                <td>The shipment is ready for recipient collection from the carrier facility.</td>
                <tr>
                <td>INVD</td>
                <td>The provided tracking number is invalid or not recognised by the carrier.</td>
                </tr>
                <tr>
                <td>ISOH</td>
                <td>The shipment is currently on hold within the carrier network. <br />
                <b><i>Note</i></b>: <i>This event code is not triggered if the customer has configured the webhook to only receive milestones.</i></td>
                </tr>
                <tr>
                <td>PSDP</td>
                <td>Shipment data has been successfully processed in the system.</td>
                </tr>
         <tr>
                <td>CAAT</td>
                <td>Collection was attempted but not completed.</td>
                </tr>
         <tr>
                <td>CAFI</td>
                <td>Collection attempt failed because the location was inaccessible.</td>
                </tr>
         <tr>
                <td>CAFP</td>
                <td>Collection attempt failed due to a packaging issue.</td>
                </tr>
         <tr>
                <td>CAFN</td>
                <td>Collection attempt failed because the shipment was not available.</td>
                </tr>
         <tr>
                <td>CAFA</td>
                <td>Collection attempt failed as there was no response at the location.</td>
                </tr>
         <tr>
                <td>CAFO</td>
                <td>Collection attempt failed due to oversize or overweight shipment.</td>
                </tr>
         <tr>
                <td>CSPP</td>
                <td>Collection from safe place failed due to a packaging issue</td>
                </tr>
         <tr>
                <td>CSPI</td>
                <td>Collection from safe place failed because access was not possible.</td>
                </tr>
         <tr>
                <td>CSPN</td>
                <td>Collection from safe place failed as the shipment was not available.</td>
                </tr>
         <tr>
                <td>CSPO</td>
                <td>Collection from safe place failed due to oversize or overweight shipment.</td>
                </tr>
         <tr>
                <td>CCAN</td>
                <td>Collection request has been cancelled.</td>
                </tr>
         <tr>
                <td>CNAT</td>
                <td>Collection was not attempted.</td>
                </tr>
                </table>
  `}</HTMLBlock>
</Accordion>

## Milestones

_Milestones_ refer to significant stages within the shipment process that are essential for monitoring process, such as order created, label printed, out for delivery, and so on.

If you choose to receive tracking milestones, bear in mind that each milestone only gets triggered once. To understand each milestone and its expected order of occurrence, refer to the information explained in the following table:

<Accordion title="Tracking Milestones" icon="fa-duotone fa-solid fa-display-chart-up">
  <Table align={["center", "left"]}>
    <thead>
      <tr>
        <th style={{ textAlign: "center" }}>
          Milestone
        </th>

        <th style={{ textAlign: "left" }}>
          Description
        </th>
      </tr>
    </thead>

    <tbody>
      <tr>
        <td style={{ textAlign: "center" }}>
          <strong>IT'S ON ITS WAY</strong>
        </td>

        <td style={{ textAlign: "left" }}>
          The shipment was handed over or is on its way to the carrier.
        </td>
      </tr>

      <tr>
        <td style={{ textAlign: "center" }}>
          <strong>IN TRANSIT</strong>
        </td>

        <td style={{ textAlign: "left" }}>
          The shipment is travelling through the carrier's network.
        </td>
      </tr>

      <tr>
        <td style={{ textAlign: "center" }}>
          <strong>TRANSIT DELAY</strong>
        </td>

        <td style={{ textAlign: "left" }}>
          The shipment processing through the carrier's network is delayed.
        </td>
      </tr>

      <tr>
        <td style={{ textAlign: "center" }}>
          <strong>IN CUSTOMS</strong>
        </td>

        <td style={{ textAlign: "left" }}>
          The shipment is undergoing customs inspections.
          <br />
          <em><code>Note</code>: this is applicable to international shipments only.</em>
        </td>
      </tr>

      <tr>
        <td style={{ textAlign: "center" }}>
          <strong>OUT FOR DELIVERY</strong>
        </td>

        <td style={{ textAlign: "left" }}>
          The shipment is on the way to the recipient.
        </td>
      </tr>

      <tr>
        <td style={{ textAlign: "center" }}>
          <strong>DELIVERY ATTEMPT FAILED</strong>
        </td>

        <td style={{ textAlign: "left" }}>
          The delivery was attempted, but failed.
        </td>
      </tr>

      <tr>
        <td style={{ textAlign: "center" }}>
          <strong>READY FOR COLLECTION</strong>
        </td>

        <td style={{ textAlign: "left" }}>
          The shipment was left at a chosen location for the recipient to collect.
        </td>
      </tr>

      <tr>
        <td style={{ textAlign: "center" }}>
          <strong>DELIVERED</strong>
        </td>

        <td style={{ textAlign: "left" }}>
          The shipment was successfully delivered to the recipient or another person or place chosen by the recipient.
        </td>
      </tr>

      <tr>
        <td style={{ textAlign: "center" }}>
          <strong>COLLECTED</strong>
        </td>

        <td style={{ textAlign: "left" }}>
          The shipment was successfully collected from the collection point.
        </td>
      </tr>

      <tr>
        <td style={{ textAlign: "center" }}>
          <strong>PART DELIVERED</strong>
        </td>

        <td style={{ textAlign: "left" }}>
          The part of a consignment shipment was delivered successfully.
        </td>
      </tr>

      <tr>
        <td style={{ textAlign: "center" }}>
          <strong>UNDELIVERABLE</strong>
        </td>

        <td style={{ textAlign: "left" }}>
          The delivery of the shipment was not possible.
        </td>
      </tr>
    </tbody>
  </Table>
</Accordion>

***

## Final events

Final events are the stages of a shipment lifecycle where no further tracking statuses are sent after the event/milestone was hit.

The following events are considered as the final events.

* All delivered events
* Recipient collected
* Shipment lost/destroyed
* Undeliverable - destroyed.

***

### See also

<Cards columns="2">
  <Card title="Set Up Tracking Webhook Connection" href="https://docs.intersoftsapient.net/v4.02/docs/create-tracking-webhook" icon="fa-solid fa-code-pull-request">
    Automate the instantaneous flow of information regarding the status of shipments.
  </Card>

  <Card title="Add Tracking Account" href="https://docs.intersoftsapient.net/docs/create-tracking-account" icon="fa-solid fa-alarm-plus">
    Establish your tracking account for seamless integration.
  </Card>

  <Card title="Handle Webhook Suspension" href="https://docs.intersoftsapient.net/docs/webhook-suspension" icon="fa-solid fa-dial-max">
    Manage and resolve webhook suspension scenarios.
  </Card>
</Cards>

<br />