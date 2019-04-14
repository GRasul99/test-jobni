<template>
  <v-layout row wrap>
    <v-flex xs12>
      <h3 slot="activator">Плюшки</h3>
        <v-list style="height: auto; max-height: 200px; overflow: auto">
          <v-list-group no-action sub-group>
            <v-list-tile slot="activator">
              <v-checkbox label="Стандартный социальный пакет" @change="qwerty()"></v-checkbox>
            </v-list-tile>
            <v-list-tile>
              <v-checkbox label="Оплачиваемый отпуск" v-model="social_packet.paid_holiday"
                @change="qwerty()"></v-checkbox>
            </v-list-tile>
            <v-list-tile>
              <v-checkbox label="Оплата больничного листа" v-model="social_packet.payment_of_sick_leave"
                @change="qwerty()"></v-checkbox>
            </v-list-tile>
            <v-list-tile>
              <v-checkbox label="Выплата декретных пособий" v-model="social_packet.payment_of_maternity_allowances"
                @change="qwerty()"></v-checkbox>
            </v-list-tile>
          </v-list-group>
          <v-list-group no-action sub-group>
            <v-list-tile slot="activator">
              <v-checkbox label="Расширенный социальный пакет" @change="qwerty()"></v-checkbox>
            </v-list-tile>
            <v-list-tile>
              <v-checkbox label="Бензин (оплата)" v-model="social_packet.gasoline" @change="qwerty()">
              </v-checkbox>
            </v-list-tile>
            <v-list-tile>
              <v-checkbox label="Амортизация (оплата)" v-model="social_packet.depreciation"
                @change="qwerty()"></v-checkbox>
            </v-list-tile>
            <v-list-group no-action sub-group>
              <v-list-tile slot="activator">
                <v-list-tile-title>
                  Проезд (оплата / наличие)
                </v-list-tile-title>
              </v-list-tile>
              <v-radio-group v-model="social_packet.travel">
                <v-radio label="Оплата" value="Оплата" @change="qwerty()"></v-radio>
                <v-radio label="Наличие" value="Наличие" @change="qwerty()"></v-radio>
                <v-radio label="Отсутствие" value="Отсутствие" @change="qwerty()"></v-radio>
              </v-radio-group>
            </v-list-group>
            <v-list-tile>
              <v-checkbox label="Сотовая связь (оплата)" v-model="social_packet.cellular_communication"
                @change="qwerty()"></v-checkbox>
            </v-list-tile>
            <v-list-group no-action sub-group>
              <v-list-tile slot="activator">
                <v-list-tile-title>
                  Детские учреждения (оплата / наличие)
                </v-list-tile-title>
              </v-list-tile>
              <v-radio-group v-model="social_packet.childcare_facilities">
                <v-radio label="Оплата" value="Оплата" @change="qwerty()"></v-radio>
                <v-radio label="Наличие" value="Наличие" @change="qwerty()"></v-radio>
                <v-radio label="Отсутствие" value="Отсутствие" @change="qwerty()"></v-radio>
              </v-radio-group>
            </v-list-group>

            <v-list-group no-action sub-group>
              <v-list-tile slot="activator">
                <v-list-tile-title>
                  Тренажерный зал (оплата / наличие)
                </v-list-tile-title>
              </v-list-tile>
              <v-radio-group v-model="social_packet.gym">
                <v-radio label="Оплата" value="Оплата" @change="qwerty()"></v-radio>
                <v-radio label="Наличие" value="Наличие" @change="qwerty()"></v-radio>
                <v-radio label="Отсутствие" value="Отсутствие" @change="qwerty()"></v-radio>
              </v-radio-group>
            </v-list-group>
            <v-list-group no-action sub-group>
              <v-list-tile slot="activator">
                <v-list-tile-title>
                  Питание (оплата / наличие)
                </v-list-tile-title>
              </v-list-tile>
              <v-radio-group v-model="social_packet.meals">
                <v-radio label="Оплата" value="Оплата" @change="qwerty()"></v-radio>
                <v-radio label="Наличие" value="Наличие" @change="qwerty()"></v-radio>
                <v-radio label="Отсутствие" value="Отсутствие" @change="qwerty()"></v-radio>
              </v-radio-group>
            </v-list-group>
            <v-list-group no-action sub-group>
              <v-list-tile slot="activator">
                <v-list-tile-title>
                  Обучение с целью повышения квалификации (оплата / наличие)
                </v-list-tile-title>
              </v-list-tile>
              <v-radio-group v-model="social_packet.childcare_facilities">
                <v-radio label="Оплата" value="Оплата" @change="qwerty()"></v-radio>
                <v-radio label="Наличие" value="Наличие" @change="qwerty()"></v-radio>
                <v-radio label="Отсутствие" value="Отсутствие" @change="qwerty()"></v-radio>
              </v-radio-group>
            </v-list-group>
            <v-list-group no-action sub-group>
              <v-list-tile slot="activator">
                <v-list-tile-title>
                  Жильё (оплата / наличие)
                </v-list-tile-title>
              </v-list-tile>
              <v-radio-group v-model="social_packet.housing">
                <v-radio label="Оплата" value="Оплата" @change="qwerty()"></v-radio>
                <v-radio label="Наличие" value="Наличие" @change="qwerty()"></v-radio>
                <v-radio label="Отсутствие" value="Отсутствие" @change="qwerty()"></v-radio>
              </v-radio-group>

            </v-list-group>
            <v-list-tile>
              <v-checkbox label="Корпоративные мероприятия (оплата)" v-model="social_packet.corporate_events"
                @change="qwerty()"></v-checkbox>
            </v-list-tile>
          </v-list-group>
        </v-list>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  data () {
    return {
      social_packet: []
    }
  }
}
</script>
