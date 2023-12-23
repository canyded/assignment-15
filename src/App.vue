<template>
  <div class = "container">
    <TextInput label="text label" placeholders = "text"/>
    <RadioBox label="who is черт?" :options="radioOptions" v-model="selectedRadio" labelColor = "#00000" />
    <PasswordInput label = "pass label" placeholders = "password"></PasswordInput>
    <NumberInput label = "number label" placeholders = "number"></NumberInput>
    <EmailInput label = "email label" placeholders = "email"></EmailInput>
    <DataPicker></DataPicker>
    <FormSelect id="mySelect" name="mySelect" label="Choose an option" :options="selectOptions"/>
    <FormTextArea id = "aha" label = "textarea" placeholder = "zhaz" required=true></FormTextArea>
    <FormCheckBox id="myCheckboxGroup"  label="zhantore qandai" :options="checkboxOptions" v-model="selectedCheckboxOptions"/>
    <FormToggles  id="myToggleGroup" label="toggles" :options="toggleOptions"  v-model="selectedToggleOptions"/>
    <MyButton label="Primary Button" @click="handlePrimaryButtonClick" />
    <MyButton label="Secondary Button" type="secondary" @click="handleSecondaryButtonClick" />
    <DropDownButton :options="dropdownOptions" v-model="selectedOption" />
    <GroupButtons :buttons="buttonOptions" v-model="selectedButtons"/>
    <Sliders :sliders="sliders" @update:sliders="updateSliders"/>
    <FormComponent id = "app"></FormComponent>
    <InputGroup></InputGroup>
    <Card image='./src/assets/3181a843-b3a2-4ef2-adc3-1b9fda2377b9.jpeg' title="Zhantore turaly fact" description="Ol taza meshok"/>
    <Accordion></Accordion>
    <Collapse title = "ozi biledigo"></Collapse>
    <ContentInfo :labels="['Label 1', 'Label 2']">
      <p>This is the content of the component.</p>
    </ContentInfo>
    <ProgressBar :progress="50" />
    
    <MessageBox title = "emaaa"></MessageBox>
    <Modal :title="'Custom Modal Title'">
      <p>This is the content of the modal. Click the close button to dismiss it.</p>
    </Modal>
    
    <Icons type="heart" />
    <Icons type="star" />
    <Icons type="check" />
    <ImageCarousel :images="carouselImages"></ImageCarousel>
    <Table :headers="tableHeaders" :rows="tableRows" />
    <List :items= "['asdasd', 'asdasdasd','asdasdasd','asdasdasdasd']" />
    <PageHeader title = "qalaisyn dosm" subtitle = 'zhaqsy dosm'></PageHeader>
    <PageFooter></PageFooter>
    <PageSBM></PageSBM>
    <SearchBar></SearchBar>
    <Breadcrumb :items="breadcrumbItems"></Breadcrumb>
    <Pagination
      :totalItems="totalItems"
      :itemsPerPage="itemsPerPage"
      :currentPage="currentPage"
      @page-change="changePage"
    />
    <Tags></Tags>
    <ListGroup :items="listItems" />
    <NavigationLink :links="navigationLinks"></NavigationLink>
    <LinkGroup :linkGroups="groupsData"></LinkGroup>\
    <Navbar></Navbar>
    <Tab :tabs="tabData">
    </Tab>
    <Drawer v-if="showDrawer">
      <p>Lorem ipsum dolor sit amet consectetur, a</p>
      <button @click="closeDrawer">Close Drawer</button>
    </Drawer>
    <Spin></Spin>
    <Divider></Divider>
    <Image source="./src/assets/3181a843-b3a2-4ef2-adc3-1b9fda2377b9.jpeg" altText="Image" />
    <TextComponent variant="headline">This is a Headline</TextComponent>
    <TextComponent variant="body">This is some body text.</TextComponent>
    <TextComponent variant="caption">This is a caption.</TextComponent>
    <UserProfile
      imageSource="./src/assets/39d8fc93-c9ea-4869-8cc9-7b217a1274fe.jpeg"
      altText="User Profile"
      userName="Aimat Chert"
      userRole="Web Developer"
    />
    <DatePicker></DatePicker>
    <GridSystem></GridSystem>
    <Line></Line>
    <Bar></Bar>
    <Circle></Circle>
    <Alert
      title="Success!"
      message="Operation completed successfully."
      variant="success"
      :autoCloseDelay="3000"
      @closed="handleAlertClosed"
    />

    <Tooltips tooltipText="This is a beautiful tooltip!">
      Hover me
    </Tooltips>
    
  </div>
  

</template>

<script>
import TextInput from "./components/TextInput.vue"; 
import RadioBox from "./components/RadioBox.vue";
import PasswordInput from "./components/PasswordInput.vue";
import NumberInput from "./components/NumberInput.vue";
import emailInput from "./components/emailInput.vue";
import EmailInput from "./components/emailInput.vue";
import DataPicker from "./components/DataPicker.vue";
import FileInput from "./components/FileInput.vue";
import FormSelect from "./components/FormSelect.vue";
import FormTextArea from "./components/FormTextArea.vue";
import FormCheckBox from "./components/FormCheckBox.vue"; 
import FormToggles from "./components/FormToggles.vue"
import MyButton from "./components/MyButton.vue"
import DropDownButton from "./components/DropDownButton.vue"
import GroupButtons from "./components/GroupButtons.vue"
import Sliders from "./components/Sliders.vue"
import FormComponent from "./components/FormComponent.vue";
import InputGroup from "./components/InputGroup.vue";
import Card from './components/Card.vue'
import Accordion from './components/Accordion.vue'
import Collapse from './components/Collapse.vue'
import ContentInfo from './components/ContentInfo.vue'
import ProgressBar from "./components/ProgressBar.vue"
import ToolTips from "./components/ToolTips.vue"
import MessageBox from './components/MessageBox.vue'
import Modal from './components/Modal.vue'
import Alert from './components/Alert.vue'
import Icons from './components/Icons.vue'
import ImageCarousel from './components/ImageCarousel.vue'
import Table from './components/Table.vue'
import List from './components/List.vue'
import PageHeader from './components/PageHeader.vue'
import PageFooter from './components/PageFooter.vue'
import PageSBM from './components/PageSBM.vue'
import SearchBar from './components/SearchBar.vue'
import Breadcrumb from './components/Breadcrumb.vue'
import Pagination from './components/Pagination.vue'
import Tags from './components/Tags.vue'
import ListGroup from './components/ListGroup.vue'
import NavigationLink from './components/NavigationLink.vue'
import LinkGroup from './components/LinkGroup.vue'
import Navbar from './components/Navbar.vue'
import Tab from './components/Tab.vue'
import Drawer from './components/Drawer.vue'
import Spin from './components/Spin.vue'
import Divider from './components/Divider.vue'
import Image from './components/Image.vue'
import TextComponent from './components/TextComponent.vue'
import UserProfile from './components/UserProfile.vue'
import DatePicker from "./components/DatePicker.vue";
import GridSystem from './components/GridSystem.vue'
import Line from './components/Line.vue'
import Bar from './components/Bar.vue'
import Circle from './components/Circle.vue'




export default {
  components: {
    TextInput,
    RadioBox,
    PasswordInput,
    NumberInput,
    emailInput,
    EmailInput,
    DataPicker,
    FileInput,
    FormSelect,
    FormTextArea,
    FormCheckBox,
    FormToggles,
    MyButton,
    DropDownButton,
    GroupButtons,
    Sliders,
    FormComponent,
    InputGroup,
    Card,
    Accordion,
    Collapse,
    ContentInfo,
    ProgressBar,
    ToolTips,
    MessageBox,
    Modal,
    Alert,
    Icons,
    ImageCarousel,
    Table,
    List,
    PageHeader,
    PageFooter,
    PageSBM,
    SearchBar,
    Breadcrumb,
    Pagination,
    Tags,
    ListGroup,
    NavigationLink,
    LinkGroup,
    Navbar,
    Tab,
    Drawer,
    Spin,
    Divider,
    Image,
    TextComponent,
    UserProfile,
    DatePicker,
    GridSystem,
    Line,
    Bar,
    Circle
},
  data() {
    return {
      parentValue: '',
      showDrawer: false,
      radioOptions: [
        { label: 'Miras', value: 'option1' },
        { label: 'Olzhas', value: 'option2' },
        { label: 'Aimat', value: 'option3' },
      ],
      selectedRadio: '',
      selectOptions: [
        { value: "option1", label: "Option 1" },
        { value: "option2", label: "Option 2" },
        { value: "option3", label: "Option 3" },
      ],
      checkboxOptions: [
        { label: '25', value: 'option1' },
        { label: '10000', value: 'option2' },
        { label: '234234', value: 'option3' },
      ],
      toggleOptions: [
        { label: 'jym', value: 'option1' },
        { label: 'study', value: 'option2' },
        { label: 'ke', value: 'option3' },
      ],
      dropdownOptions: [
        { label: 'dosm', value: 'option1' },
        { label: 'dosm2', value: 'option2' },
        { label: 'dosm3', value: 'option3' },
      ],
      tabData: [
        { label: 'Tab 0dsdsdfs' },
        { label: 'Tab sdsd1' },
        { label: 'Tasdsdb 2' },
      ],
      selectedOption: { label: 'Option 1', value: 'option1' },
      buttonOptions: [
        { label: 'Button 1', value: 'button1' },
        { label: 'Button 2', value: 'button2' },
        { label: 'Button 3', value: 'button3' },
      ],
      selectedButtons: [], 
      sliders: [
        { id: 'slider1', label: 'volume', min: 0, max: 100, value: 50 },
        { id: 'slider2', label: 'dosm', min: 0, max: 10, value: 5 },
      ],
      carouselImages: [
        './src/assets/3181a843-b3a2-4ef2-adc3-1b9fda2377b9.jpeg',
        './src/assets/26e29989-7e2b-4e98-b50f-96038129a15c.jpeg',
        './src/assets/f5e2e219-2382-4b9c-b167-13cc1af7dfb1.jpeg',
      ],
      listItems: ['aa', 'bb', 'cc', 'aa', 'ddddd'],
      tableHeaders: ['ID', 'Name', 'Age', 'Country'],
      tableRows: [
        [1, 'John Doe', 25, 'USA'],
        [2, 'Jane Smith', 30, 'Canada'],
        [3, 'Bob Johnson', 22, 'UK'],
      ],
      breadcrumbItems: [
        { label: 'Home', link: '/' },
        { label: 'Products', link: '/products' },
        { label: 'Category A', link: '/products/category-a' },
        { label: 'Current Page' },
      ],
      totalItems: 100,
      itemsPerPage: 10,
      currentPage: 1,
      navigationLinks: [
        { label: 'Home', url: '/' },
        { label: 'About', url: '/about' },
        { label: 'Services', url: '/services' },
        { label: 'Contact', url: '/contact' },
      ],
      
      groupsData: [
        {
          title: 'Group 1',
          links: [
            { label: 'Link 1.1', url: '/link1.1' },
            { label: 'Link 1.2', url: '/link1.2' },
            { label: 'Link 1.3', url: '/link1.3' },
          ],
        },
        {
          title: 'Group 2',
          links: [
            { label: 'Link 2.1', url: '/link2.1' },
            { label: 'Link 2.2', url: '/link2.2' },
          ],
        },
      ],
      

    }
    },
    methods: {
    updateSliders(updatedSliders) {
      this.sliders = updatedSliders;
    },
    changePage(newPage) {
      this.currentPage = newPage;
      console.log('Current Page:', newPage);
    },
    openDrawer() {
      this.showDrawer = true;
    },
    closeDrawer() {
      this.showDrawer = false;
    },
    handleAlertClosed() {
      console.log('Alert closed!');
    },
  },

  };
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  gap: 30px;
}
</style>
 

