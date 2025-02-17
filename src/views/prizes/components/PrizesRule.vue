<template>
  <div id="prizes-rule" class="prizes-rule">
    <div class="rule-title">Terms and Conditions</div>
    <div class="prizes-rule-card">
      <div v-for="(item, index) in ruleList" :key="index">
        <div class="card-label">{{ item.label }}</div>
        <div v-if="item.image" class="image">
          <img :src="require(`../../../assets/prizes/${item.image}`)" alt="" />
        </div>
        <div
          class="card-rule-text"
          v-for="(option, idx) in item.text"
          :key="idx"
          v-html="option"
        ></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PrizesRule',
  data() {
    return {
      ruleList: [
        {
          label: '1.Which networks are participating in this event?',
          text: [
            '- Bridge from specific networks to Optimism Superchain.',
            '- Optimism Superchain includes: Optimism, Base, Mode, Cyber, Bob, Mint, Kroma, Lisk, Zora',
            '- Specific Chains include: Ethereum, Arbitrum, linea,scroll,zkSync Lite, Polygon, Loopring, zkSyncEra, BNB Chain, Arbitrum Nova, Mantle, opBNB, X Layer, Manta, zkFair, Blast, zkLink Nova, Proof of Play Apex, BEVM, Core, Bitlayer, BounceBit, Optopia, AlienxChain, Fraxtal, Zircuit, Fuse',
            '<span class="orbiter_global_prizes_rule_tag">1.1 Which networks are added  in Extended Session?</span>',
            '<span class="orbiter_global_prizes_rule_tag">- Bridge from specific networks to Scroll Chain or bridge from Scroll Chain to specific networks.</span>',
            '-Specific networks include: Ethereum, Arbitrum, linea, zkSync Lite, Polygon, Loopring, zkSyncEra, BNB Chain, Arbitrum Nova, Mantle, opBNB, X Layer, Zora, Manta, zkFair, Blast, zkLink Nova, Proof of Play Apex, BEVM, Core, Bitlayer, BounceBit, Optopia, AlienxChain, Fraxtal, Zircuit, Fuse, Optimism, Base, Mode, Cyber, Bob, Mint, Kroma, Lisk',
            '- The minimum amount required: 0.03 ETH',
            '- Bridge token: ETH',
          ],
        },
        {
          label:
            '2.How to share the prize pool and extra bonus?',
          text: [
            '- Complete <span class="orbiter_global_prizes_rule_tag">≥3 transactions </span> to qualify for a share of the prize pool.',
            '<span class="orbiter_global_prizes_rule_tag">- Prize Pool Breakdown:</span>',
            '&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- <span class="orbiter_global_prizes_rule_tag">≥3 TX Traders:</span> Share 40% of the prize pool.',
            '&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- <span class="orbiter_global_prizes_rule_tag">Top 9-100 Traders (with ≥20 TX):</span> Share 35% of the prize pool.',
            '&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- <span class="orbiter_global_prizes_rule_tag">Top 1-8 Traders (with ≥20 TX):</span> Share 25% of the prize pool.',
            '- The ranking is determined based on transactions. If users have the same number of transactions, ranking will be based on the transaction value. More transactions, greater chance to win!',
            '<span class="orbiter_global_prizes_rule_tag">- Extra bonus: </span>',
            '&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span class="orbiter_global_prizes_rule_tag">- Rank in the top 5 fastest traders daily (Bridge at least 3000 TXs daily): </span> earn a 200 $USDC daily bonus.',
            '- In Tier 1 - Tier 5: An address can receive a maximum extra bonus of <span class="orbiter_global_prizes_rule_tag">3,000  $USDC</span>.',
            '- In Extended Session: An address can receive a maximum extra bonus of <span class="orbiter_global_prizes_rule_tag">1,600 $USDC</span>.',
            '- The ranking is determined based on transactions and daliy completed time. If users have the same number of transactions within the same time frame, ranking will be based on the transactions. More transactions, greater chance to win!',
            '- Note: ',
            '- We have allocated $23,000 as a total extra bonus for the top 5 fastest traders daily. Only users who meet the requirement of bridging at least 3,000 transactions (TXs) daily will be eligible for the extra bonus. If the number of users who qualify for the reward does not reach 5 per day, the rewards will not be fully distributed.'
          ],
        },
        {
          label:
            '3.What are the rules of different prize pool tiers and bridging fee rebates?',
          image: 'rule.png',
          text: [
            '<span class="orbiter_global_prizes_rule_tag">Note:</span>',
            'In Tiers 1~5:',
            '- The prize pool will be unlocked when the amount of transactions (TX) ≥ 4,000;',
            '- TOP 1 to 8 users, up to 96% bridging fees (except for gas fees) will be rebated.',
            '<span class="orbiter_global_prizes_rule_tag">In Extended session: </span>',
            '<span class="orbiter_global_prizes_rule_tag">- TOP 1 users, 98% bridging fees (except for gas fees) will be rebated.</span>',
            '<span class="orbiter_global_prizes_rule_tag">- TOP 2 to 8 users, 96% bridging fees (except for gas fees) will be rebated.</span>',
            '<span class="orbiter_global_prizes_rule_tag">- Top 100 shares extend the $7000 prize pool.</span>',
          ],
        },
        {
          label: '4.How to Earn O-Points Rewards?',
          text: [
            'Participants can earn additional event points by completing the following tasks:',
            '- Complete ≥3 transactions for 7 days to earn extra 150 Opoints.',
            '- Complete ≥3 transactions for 14 days to earn extra 450 Opoints.',
            '<span class="orbiter_global_prizes_rule_tag">Note:</span>',
            '- One address can receive a maximum of 450 Opoints.'
          ],
        },
        {
          label: '5.When will the rewards be distributed?',
          text: [
            '- All rewards will be distributed after the event ends.',
            '- Please stay informed and claim your rewards within 3 days of the reward claim portal opening!',
          ],
        },
      ],
    }
  },
}
</script>

<style scoped lang="scss">
.prizes-rule {
  width: 100%;
  margin: 80px 0 200px;
  .rule-title {
    width: 100%;
    font-size: 32px;
    font-weight: 600;
    line-height: 44px;
    letter-spacing: 0px;
    text-align: center;
  }
  .prizes-rule-card {
    padding: 8px 24px 24px;
    width: 100%;
    border: 4px solid rgb(69, 35, 48);
    background: radial-gradient(
        96% 96% at 50% 50%,
        rgba(27, 21, 37, 0) 1.849%,
        rgba(255, 70, 68, 0.2) 100%
      ),
      rgb(18, 4, 30);
    text-align: left;
    margin-top: 16px;
    .card-label {
      margin-top: 16px;
      font-size: 16px;
      font-weight: 600;
      line-height: 28px;
      letter-spacing: 0px;
      font-family: GeneralSans-SemiBold;
      margin-top: 16px;
    }

    .image {
      width: 100%;
      margin-top: 12px;
      img {
        width: 100%;
      }
    }

    .card-rule-text {
      font-size: 14px;
      font-weight: 400;
      line-height: 23px;
      letter-spacing: 0px;
      color: rgba(255, 255, 255, 0.6);
    }
  }
}

@media (max-width: 740px) {
  #prizes-rule {
    width: 100%;
    margin: 32px 0 60px;
    .prizes-rule-card {
      padding: 8px 16px;
    }
    .rule-title {
      font-size: 24px;
    }
  }
}
</style>
