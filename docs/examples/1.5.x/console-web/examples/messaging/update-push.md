import { Client, Messaging, MessagePriority } from "@appwrite.io/console";

const client = new Client()
    .setEndpoint('https://cloud.appwrite.io/v1') // Your API Endpoint
    .setProject('<YOUR_PROJECT_ID>'); // Your project ID

const messaging = new Messaging(client);

const result = await messaging.updatePush(
    '<MESSAGE_ID>', // messageId
    [], // topics (optional)
    [], // users (optional)
    [], // targets (optional)
    '<TITLE>', // title (optional)
    '<BODY>', // body (optional)
    {}, // data (optional)
    '<ACTION>', // action (optional)
    '[ID1:ID2]', // image (optional)
    '<ICON>', // icon (optional)
    '<SOUND>', // sound (optional)
    '<COLOR>', // color (optional)
    '<TAG>', // tag (optional)
    null, // badge (optional)
    false, // draft (optional)
    '', // scheduledAt (optional)
    false, // contentAvailable (optional)
    false, // critical (optional)
    MessagePriority.Normal // priority (optional)
);

console.log(result);
