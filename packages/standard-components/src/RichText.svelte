<script>
  import { getContext } from "svelte"
  import { RichText } from "@budibase/bbui"

  const { styleable } = getContext("sdk")
  const component = getContext("component")

  export let value = ""

  // Need to determine what options we want to expose.
  let options = {
    modules: {
      toolbar: [
        [
          {
            header: [1, 2, 3, false],
          },
        ],
        ["bold", "italic", "underline", "strike"],
      ],
    },
    placeholder: "Type something...",
    theme: "snow",
  }
</script>

<div use:styleable={$component.styles}>
  <RichText bind:value {options} />
</div>
