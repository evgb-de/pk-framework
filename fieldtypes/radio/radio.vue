<template>

    <div :class="classes(['uk-form-row'], field.data.classSfx)">
        <span class="uk-form-label" v-show="!field.data.hide_label">{{ fieldLabel | trans }}
            <a v-if="field.data.help_text && field.data.help_show == 'tooltip_icon'"
               class="uk-icon-info uk-icon-hover uk-margin-small-top uk-float-right"
               :title="field.data.help_text" data-uk-tooltip="{delay: 100}"></a>
        </span>

        <div class="uk-form-controls uk-form-controls-text">
            <p v-for="option in field.options" class="uk-form-controls-condensed">
                <label><input type="radio" value="{{ option.value }}"
                              v-model="inputValue"> {{ option.text }}</label>
            </p>
        </div>

        <p v-if="field.data.help_text && field.data.help_show == 'block'"
           class="uk-form-help-block">{{{field.data.help_text}}}</p>

    </div>

</template>

<script>
/*global _ */

import BixieFieldtypeMixin from '../../app/mixins/fieldtype';

export default {

    name: 'FieldtypeRadio',

    mixins: [BixieFieldtypeMixin,],

    settings: {},

    appearance: {},

    data: () => ({
        fieldid: _.uniqueId('bixiefieldtype_'),
    }),

};

</script>
