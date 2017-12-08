# WPB Custom Shortcodes

Написать базовые шорткоды:
Раздел,
Строка,
Текстовый блок,
Заголовок,
Изображение,
Кнопка

Нарисовать базовые иконки:

### Стартовый шорткат
```
<?php

// Shortcode
add_shortcode( 'vc_NAME', 'vc_NAME_shortcode' );

function vc_NAME_shortcode( $atts ) {
  extract( shortcode_atts( array(
    'PARAM_NAME' => 'DEFAULT VALUE',
  ), $atts ) );

  return "";
}

// Action
add_action( 'vc_before_init', 'vc_NAME_action' );

function vc_NAME_action() {
  vc_map( array(
    'name' => __( 'NAME', 'js_composer' ),
    'base' => 'vc_NAME',
    'description' => '',
    'category' => __( 'CATEGORY_NAME', 'js_composer' ),
    'icon' => get_template_directory_uri() . '/vc_templates/vc-element-icons/element-icon-_NAME.svg',
    'params' => array(
    
    )
  ) );
}

?>
```

### Textfield
```
array(
  'type' => 'textfield',
  'heading' => __( 'Text', 'js_composer' ),
  'param_name' => 'text',
  'description' => __( '', 'js_composer' ),
),
```

### Button 
Описание
```
array(
  'type' => 'vc_link',
  'heading' => __( 'Button', 'js_composer' ),
  'param_name' => 'button',
  'description' => __( '', 'js_composer' ),
),
```

### Dropdown
Описание
```
array(
  'type' => 'dropdown',
  'heading' => __( 'Dropdown', 'js_composer' ),
  'param_name' => 'dropdown',
  'description' => __( '', 'js_composer' ),
  'value' => array(
    __( 'Value 1', 'js_composer' ) => 'value_1',
    __( 'Value 2', 'js_composer' ) => 'value_2',
  ),
),
```

### Add param 
```
'admin_label' => true,
```

#### Зависимость от выбираемого значение одного из полей, например dropdown
```
'dependency' => array(
  'element' => 'param_name', // param_name
  'value' => 'value_1',
),
```

```
Добавление новых шорткодов в файле function.php

/*------------------------------------------------------------------*
 * Add VC Elements Custom
/*------------------------------------------------------------------*/

get_template_part( 'vc_templates/vc_NAME' );
```