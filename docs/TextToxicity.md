# Text Toxicity

Ideal for things like customer reviews or somewhere you need to review what user writes before it gets sent. A pre-check before your server has to do the work.

## Sample Usage

    <script>
        let sample = [
            {
            text: "We're dudes on computers, moron.  You are quite astonishingly stupid.",
            },
            {
            text: 'Please stop. If you continue to vandalize Wikipedia, as you did to Kmart, you will be blocked from editing.',
            },
            {
            text: 'I respect your point of view, and when this discussion originated on 8th April I would have tended to agree with you.',
            },
        ]
    </script>
    <TextToxicity  {samples} verbose={true} on:prediction={yourHandlerFunction}
        let:modelsLoaded
        let:predictions
        let:labels>
        <!-- Your reactive code here -->
    </TextToxicity>

\* **samples** is required

## API

| Parameter   | Type               | Description                                                                         |
| ----------- | ------------------ | ----------------------------------------------------------------------------------- |
| **samples** | _array of objects_ | The sentences to evaluate are in the 'text' field. E.g. `[{text: 'text to check'}]` |
| **verbose** | _boolean_          | enabled console logging for debugging purposes. Defaults to false                   |

## Events

| Parameter         | Type               | Description                                                                                                                                                |
| ----------------- | ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **on:prediction** | _array of objects_ | Triggered when a prediction is made. Allows processing in the caller component's `<script>` not in the markup, which is mostly useful for rendering state. |

## 🎰 Slot variables

| Parameter            | Type               | Description                                              |
| -------------------- | ------------------ | -------------------------------------------------------- |
| **let:predictions**  | _array of objects_ | The raw array of poses prediction made by the model      |
| **let:labels**       | _array of objects_ | See what labels were being used by the model to predict  |
| **let:model**        | _object_           | The model being used                                     |
| **let:modelsLoaded** | _object_           | Useful for loading indication while the model is loading |
