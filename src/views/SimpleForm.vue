<template>
  <div>
    <h1>Create an event</h1>
    <form>
      <BaseSelect
      :options="categories"
      v-model="event.category"
      labbel="select a catagory"
      />
      <h3>Name & describe your event</h3>
      <BaseInput
        v-model="event.title"
        label="Title"
        type="text"
      />
      <label>Description</label>

      <BaseInput
        v-model="event.description"
        label="Description"
        type="text"
      />

      <h3>Where is your event?</h3>
      <BaseInput
      v-model="event.location"
      label="Location"
      type="text"
      />
      <hr/>
      {{ event }}

      <h3>Are pets allowed?</h3>
      <div>
        <BaseRadioGroup
          v-model="event.pets"
          name="pets"
          :options = "petOptions"
        />
      </div>

      <h3>Extras</h3>
      <div>
        <BaseCheckbox
          label="Catering"
          v-model="event.extras.catering"
        />
      </div>
      <div>
        <BaseCheckbox
          label="Live music"
          v-model="event.extras.music"
        />
      </div>

      <button class="button -fill-gradient" type="submit">Submit</button>
    </form>
  </div>
</template>

<script>

export default {
  data () {
    return {
      categories: [
        'sustainability',
        'nature',
        'animal welfare',
        'housing',
        'education',
        'food',
        'community'
      ],
      event: {
        category: '',
        title: '',
        description: '',
        location: '',
        pets: 1,
        extras: {
          catering: false,
          music: false
        }
      },
      petOptions: [
        { label: 'Yes', value: 1 },
        { label: 'No', value: 0 }
      ]
    }
  }
}
</script>
