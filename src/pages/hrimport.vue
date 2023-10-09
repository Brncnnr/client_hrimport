<template>
  <div class="tui-hrimport">
    <div class="hrimport-heading">
      <h1>{{ $str('heading', 'local_hrimport') }}</h1>
    </div>
    <Tabs selected="hrimportuser-tab-0" content-spacing="large">
      <Tab
        :id="'hrimportuser-tab-0'"
        :name="$str('tabuser', 'local_hrimport')"
        :always-render="true"
      >
        <TabUser /> 
      </Tab>
      <Tab
        :id="'hrimportuser-tab-1'"
        :name="$str('tabjob', 'local_hrimport')"
        :always-render="true"
      >
      </Tab>
      <Tab
        :id="'hrimportuser-tab-2'"
        :name="$str('taborg', 'local_hrimport')"
        :always-render="true"
      >
      </Tab>
      <Tab
        :id="'hrimportuser-tab-3'"
        :name="$str('tabpos', 'local_hrimport')"
        :always-render="true"
      >
      </Tab>
    </Tabs>
  </div>
</template>
   
  <script>
import Tab from 'tui/components/tabs/Tab';
import Tabs from 'tui/components/tabs/Tabs';
import TabUser from '../components/TabUser';

// import Userdata from '/home/brncnnr/gitlab/totara/totaradata/sitedataAlex/hrimport/users.json';

export default {
  components: {
    Tabs,
    Tab,
    TabUser,
  },
  data() {
    return {
      // Userdata: Userdata,
    };
  },
};
</script>

<lang-strings>
  {
    "local_hrimport": [
      "heading",
      "tabuser",
      "tabjob",
      "tabpos",
      "taborg"
    ]
  }
</lang-strings>