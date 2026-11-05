Jungle Cat 2D Retro Jump n Run game in mind to bring it later to an original atari falcon machine.
gnerated from scratch with arround 30  different ai tools for sound, graphics, animation clips,tts, video
using my daily credits 6 weeks to creaate this game with super smooth sprite animations

FIRST JUNGLE-CAT.ZIP is the high end browser version game in 800 to 600 resolution at the moment 0.98, 
later follows the atari version in 320*240 ...


everything in this game you can change yourself ... there are arround 250 variables
speed for every enenmy,hero,bullet, arrows and so on ... 
jump height, but also sprite size scaling, and even how much frames a sprite animation should have

so if you have 12 frames for the hero run loop and you want 32 frames
change variable from 12 to 32 and add the frames in graphics folder same size
or change variables to scale smaller or bigger

as example:

1. THE END BOSS            (search: BOSS_FIRE_TICKS   and   function bossInit)
------------------------------------------------------------------------------------------
  BOSS_FIRE_TICKS = 120    ticks between two shots (120 = one shot every 2 seconds). Higher = easier.
  BOSS_BULLET_SPEED = 1.3  speed of the bullets (was 2.3). Lower = easier.
  hp:12                    (in bossInit)  boss health = number of hits (12 hits). Also hp0:12 - change both.
  cool:70                  (in bossInit)  ticks before the first shot after the fight starts.
  b.sh=24;b.nx=17          (in bossUpd)   length of the shoot animation / moment the bullet leaves.
                           Keep BOSS_FIRE_TICKS larger than 24.
  mv*.3*dt                 (in bossUpd)   boss walking speed (.3).
  dist>105 / dist<48       (in bossUpd)   boss walks toward you when farther than 105, backs off when
                           closer than 48.
  dist<150                 (in bossUpd)   boss only shoots when you are closer than 150 units.
  P.x>17600                (in bossUpd)   the fight starts when you pass this x position.
  17982                    (in bossUpd)   invisible wall in the arena that holds you in.
  bx=[17780,17950]         left/right limit the boss may walk to.
  l:300                    (in bossFire)  how long a bullet flies (ticks) before it vanishes.
  b.hc=14                  (in bossHit)   ticks the boss is protected after a hit.
  G.score+=5000            (in bossHit)   score for killing the boss.












<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Jungle Cat – Expert Settings</title>
<style>
:root{--bg:#fbfaf4;--ink:#1d2a1c;--mute:#5b6b58;--line:#d9d6c4;--head:#e9efd9;--acc:#2f7a1f;--code:#f0eedf}
@media (prefers-color-scheme:dark){:root{--bg:#07120a;--ink:#f4f0d8;--mute:#9fb29a;--line:#2b3a2a;--head:#13281a;--acc:#7cf000;--code:#0d1d12}}
body{margin:0;padding:24px;background:var(--bg);color:var(--ink);font:15px/1.5 system-ui,Segoe UI,Arial,sans-serif}
main{max-width:1100px;margin:0 auto}
h1{margin:0 0 4px}p.sub{margin:0 0 16px;color:var(--mute)}
nav{display:flex;flex-wrap:wrap;gap:8px;margin:12px 0}nav a{padding:4px 10px;border:1px solid var(--line);border-radius:999px;color:var(--ink);text-decoration:none;font-size:13px}nav a:hover{border-color:var(--acc)}
#q{width:100%;box-sizing:border-box;padding:10px 12px;font-size:15px;border:1px solid var(--line);border-radius:8px;background:var(--code);color:var(--ink)}
h2{margin:28px 0 8px;font-size:18px;color:var(--acc)}h2 small{color:var(--mute);font-weight:400}
.wrap{overflow-x:auto}
table{width:100%;border-collapse:collapse;font-size:14px}
th,td{text-align:left;padding:6px 10px;border-bottom:1px solid var(--line);vertical-align:top}
th{background:var(--head);position:sticky;top:0}
td:nth-child(2),td:nth-child(3){white-space:nowrap}
code{background:var(--code);padding:1px 6px;border-radius:4px;font-size:13px}
.new{background:var(--acc);color:var(--bg);border-radius:4px;padding:0 6px;font-size:11px;font-weight:700;text-transform:uppercase}
tr.hide,section.hide{display:none}
</style>
</head>
<body>
<main>
<h1>Jungle Cat – Expert Settings</h1>
<p class="sub">281 variables in 12 groups. Defaults are the values in <code>js/game.js</code>. Step is the amount one click on the setting changes.</p>
<input id="q" type="search" placeholder="Search a variable or a word, e.g. BOSS, speed, FRAMES …" aria-label="Search settings">
<nav><a href="#hero-movement">Hero Movement</a> <a href="#hero-weapons">Hero Weapons</a> <a href="#enemies">Enemies</a> <a href="#archer-10">Archer 10</a> <a href="#archer-30">Archer 30</a> <a href="#gorilla">Gorilla</a> <a href="#woman-boss">Woman Boss</a> <a href="#screen-misc">Screen / Misc</a> <a href="#chimp">Chimp</a> <a href="#princess-dance">Princess / Dance</a> <a href="#red-gems">Red Gems</a> <a href="#animation-frames">Animation Frames</a></nav>
<div class="wrap">
<section class="grp" id="hero-movement"><h2>Hero Movement <small>(65)</small></h2>
<table><thead><tr><th>Variable</th><th>Default</th><th>Step</th><th>What it does</th></tr></thead><tbody>
<tr><td><code>HERO_WALK_SPEED</code></td><td>0.65</td><td>0.01</td><td>walking / running speed on the ground</td></tr>
<tr><td><code>HERO_CROUCH_SPEED</code></td><td>0.35</td><td>0.01</td><td>walking speed while crouching</td></tr>
<tr><td><code>HERO_SWIM_SPEED</code></td><td>0.55</td><td>0.01</td><td>swimming speed in the water (sideways)</td></tr>
<tr><td><code>HERO_AIR_SPEED_FACTOR</code></td><td>1.9</td><td>0.1</td><td>sideways speed in the air = walk speed x this (the hero flies further in a jump)</td></tr>
<tr><td><code>HERO_ROPE_SPEED</code></td><td>0.75</td><td>0.01</td><td>speed while hanging on a rope hole</td></tr>
<tr><td><code>HERO_CLIMB_SPEED</code></td><td>0.7</td><td>0.01</td><td>speed climbing up / down a vine</td></tr>
<tr><td><code>HERO_JUMP_SPEED</code></td><td>2.975</td><td>0.1</td><td>start speed of a jump upwards</td></tr>
<tr><td><code>HERO_GRAVITY</code></td><td>0.095</td><td>0.001</td><td>falling: speed gained every tick</td></tr>
<tr><td><code>HERO_MAX_FALL_SPEED</code></td><td>4.5</td><td>0.1</td><td>falling never gets faster than this</td></tr>
<tr><td><code>HERO_CLIMB_JUMP_SPEED</code></td><td>2.4</td><td>0.1</td><td>jump off a vine</td></tr>
<tr><td><code>HERO_CLIMB_TOP_HOP</code></td><td>2</td><td>1</td><td>little hop when she climbs over the top of a vine</td></tr>
<tr><td><code>HERO_ROPE_HOP_UP</code></td><td>1.6</td><td>0.1</td><td>hop up at the end of a rope hole</td></tr>
<tr><td><code>HERO_ROPE_HOP_SIDE</code></td><td>0.65</td><td>0.01</td><td>hop sideways at the end of a rope hole</td></tr>
<tr><td><code>HERO_SPIKE_BOUNCE</code></td><td>2.5</td><td>0.1</td><td>bounce up after she touched spikes</td></tr>
<tr><td><code>HERO_WATER_TICKS</code></td><td>600</td><td>10</td><td>ticks in the deep water until she is eaten / drowns (600 = 10 seconds)</td></tr>
<tr><td><code>HERO_HURT_INVULN</code></td><td>80</td><td>5</td><td>ticks she can not be hurt again after a hit</td></tr>
<tr><td><code>SWIM_SINK</code></td><td>0.04</td><td>0.001</td><td>swimming: she sinks by this every tick</td></tr>
<tr><td><code>SWIM_DIVE</code></td><td>0.1</td><td>0.01</td><td>swimming: extra downward push while the DOWN key is held</td></tr>
<tr><td><code>SWIM_RISE</code></td><td>0.18</td><td>0.01</td><td>swimming: upward push while UP / JUMP is held</td></tr>
<tr><td><code>SWIM_MAX_UP</code></td><td>1</td><td>1</td><td>swimming: fastest way up</td></tr>
<tr><td><code>SWIM_MAX_DOWN</code></td><td>0.8</td><td>0.01</td><td>swimming: fastest way down</td></tr>
<tr><td><code>HOLE_POST_W</code></td><td>10</td><td>1</td><td></td></tr>
<tr><td><code>JUMP_SLOW</code></td><td>0.704</td><td>0.01</td><td></td></tr>
<tr><td><code>HERO_SLOW</code></td><td>0.85</td><td>0.01</td><td></td></tr>
<tr><td><code>VINE_G</code></td><td>0.19</td><td>0.01</td><td>swing gravity of the swinging vines (was .38, faster).</td></tr>
<tr><td><code>VINE_LAUNCH</code></td><td>1.41</td><td>0.1</td><td>swing gravity (was .38 = faster) and a launch boost so the jump distance stays the same</td></tr>
<tr><td><code>RUN_ANIM_K</code></td><td>1.4</td><td>0.1</td><td></td></tr>
<tr><td><code>HANG_K</code></td><td>0.95</td><td>0.01</td><td>size of the vine-hang animation (1 = as exported)</td></tr>
<tr><td><code>JAPEX</code></td><td>20</td><td>1</td><td>which picture (0-44) is shown at the top of the jump.</td></tr>
<tr><td><code>JRATE</code></td><td>1.7</td><td>0.1</td><td>max pictures per tick (higher = snappier changes).</td></tr>
<tr><td><code>JLAND</code></td><td>18</td><td>1</td><td>launch speed, apex frame (0-based), max frames per tick, ground distance where the landing reach starts</td></tr>
<tr><td><code>RESP_SAFE</code></td><td>1</td><td>1</td><td></td></tr>
<tr><td><code>RESP_BACK</code></td><td>34</td><td>5</td><td></td></tr>
<tr><td><code>RESP_MAX</code></td><td>260</td><td>10</td><td></td></tr>
<tr><td><code>RESP_HOLE</code></td><td>60</td><td>5</td><td></td></tr>
<tr><td><code>RESP_ENEMY</code></td><td>110</td><td>10</td><td></td></tr>
<tr><td><code>RESP_HIT</code></td><td>1</td><td>1</td><td></td></tr>
<tr><td><code>FADE_OUT</code></td><td>70</td><td>5</td><td></td></tr>
<tr><td><code>FADE_IN</code></td><td>45</td><td>5</td><td></td></tr>
<tr><td><code>SWK</code></td><td>1.12</td><td>0.1</td><td>size of the swimming picture.</td></tr>
<tr><td><code>IK</code></td><td>1.1</td><td>0.1</td><td></td></tr>
<tr><td><code>HID_STEP</code></td><td>110</td><td>10</td><td>hero idle: ticks one pose is held (the 6 new pictures play 1-2-3-4-5-6-5-4-3-2-1 ... and fade into each other).</td></tr>
<tr><td><code>HID_FADE</code></td><td>0</td><td>1</td><td>part of every step used to fade into the next picture (0 = hard cut, 1 = always fading).</td></tr>
<tr><td><code>IW</code></td><td>1.22</td><td>0.1</td><td>height / width factor of the idle pose.</td></tr>
<tr><td><code>DUCK_K</code></td><td>0.9</td><td>0.01</td><td>duck pose size</td></tr>
<tr><td><code>CROUCH_ANIM</code></td><td>1</td><td>1</td><td>1 = new crouch-down animation, 0 = old single picture.</td></tr>
<tr><td><code>CD_DN</code></td><td>24</td><td>5</td><td>ticks to go down.</td></tr>
<tr><td><code>CD_UP</code></td><td>16</td><td>1</td><td>ticks to stand up.</td></tr>
<tr><td><code>CD_DZ</code></td><td>0.24</td><td>0.01</td><td>share of the time spent dissolving into the hold pose.</td></tr>
<tr><td><code>CLIMB_ON</code></td><td>1</td><td>1</td><td>0 = old pose (run picture), 1 = the new climbing animation (33 pictures)</td></tr>
<tr><td><code>CLIMB_FPT</code></td><td>0.5</td><td>0.01</td><td>pictures per game tick while she climbs (60 ticks/s -&gt; 30 pictures/s). Up = forward,</td></tr>
<tr><td><code>CLIMB_K</code></td><td>0.165</td><td>0.01</td><td>game units per picture pixel (size). CLIMB_AX / CLIMB_AY = point of the picture that sits on</td></tr>
<tr><td><code>CLIMB_AX</code></td><td>147</td><td>10</td><td></td></tr>
<tr><td><code>CLIMB_AY</code></td><td>315</td><td>10</td><td></td></tr>
<tr><td><code>CLIMB_DY</code></td><td>2</td><td>1</td><td></td></tr>
<tr><td><code>ROPE_ON</code></td><td>1</td><td>1</td><td>0 = old pose (run picture + drawn arms), 1 = the hand-over-hand animation</td></tr>
<tr><td><code>ROPE_FPT</code></td><td>0.7</td><td>0.01</td><td></td></tr>
<tr><td><code>ROPE_K</code></td><td>0.16</td><td>0.01</td><td>game units per picture pixel (size of the animation). ROPE_AX / ROPE_AY = the point of</td></tr>
<tr><td><code>ROPE_AX</code></td><td>120</td><td>10</td><td></td></tr>
<tr><td><code>ROPE_AY</code></td><td>31</td><td>5</td><td></td></tr>
<tr><td><code>ROPE_TILT</code></td><td>0.5</td><td>0.01</td><td></td></tr>
<tr><td><code>VL_ON</code></td><td>1</td><td>1</td><td>0 = off (old behaviour).</td></tr>
<tr><td><code>VL_TPF</code></td><td>1.7</td><td>0.1</td><td>game ticks per leap picture (19 pictures in about 32 ticks, the last one is held).</td></tr>
<tr><td><code>VL_HOLD</code></td><td>10</td><td>1</td><td></td></tr>
<tr><td><code>VL_AY</code></td><td>25</td><td>5</td><td></td></tr>
</tbody></table></section>
<section class="grp" id="hero-weapons"><h2>Hero Weapons <small>(22)</small></h2>
<table><thead><tr><th>Variable</th><th>Default</th><th>Step</th><th>What it does</th></tr></thead><tbody>
<tr><td><code>WHIP_COOLDOWN</code></td><td>26</td><td>5</td><td>ticks before the next whip hit</td></tr>
<tr><td><code>MACE_COOLDOWN</code></td><td>18</td><td>1</td><td>ticks before the next mace hit</td></tr>
<tr><td><code>KNIFE_COOLDOWN</code></td><td>20</td><td>1</td><td>ticks before the next knife throw</td></tr>
<tr><td><code>KNIFE_SPEED</code></td><td>5</td><td>1</td><td>flying speed of a thrown knife (the hero&#x27;s &quot;bullet&quot;)</td></tr>
<tr><td><code>KNIFE_LIFE</code></td><td>80</td><td>5</td><td>ticks a knife flies before it disappears</td></tr>
<tr><td><code>WH_T</code></td><td>21</td><td>5</td><td>ticks of one whip swing (smaller = faster).</td></tr>
<tr><td><code>WH_A0</code></td><td>-1.55</td><td>0.1</td><td>start angle.</td></tr>
<tr><td><code>WH_A1</code></td><td>0.5</td><td>0.01</td><td>end angle (guide arc for jumps / hanging).</td></tr>
<tr><td><code>WH_LAG</code></td><td>0.38</td><td>0.01</td><td>how much the tip trails behind (the &quot;crack&quot;).</td></tr>
<tr><td><code>WA_LAG</code></td><td>2.5</td><td>0.1</td><td>same for the standing whip-attack pictures.</td></tr>
<tr><td><code>WP_N</code></td><td>22</td><td>5</td><td></td></tr>
<tr><td><code>WP_ST</code></td><td>1.656</td><td>0.1</td><td></td></tr>
<tr><td><code>WP_HD</code></td><td>4</td><td>1</td><td></td></tr>
<tr><td><code>WP_G</code></td><td>0.085</td><td>0.001</td><td></td></tr>
<tr><td><code>WP_DAMP</code></td><td>0.985</td><td>0.01</td><td></td></tr>
<tr><td><code>WP_BEND</code></td><td>0.2</td><td>0.01</td><td></td></tr>
<tr><td><code>WP_DRV</code></td><td>0.26</td><td>0.01</td><td></td></tr>
<tr><td><code>WP_FADE</code></td><td>30</td><td>5</td><td></td></tr>
<tr><td><code>WP_W1</code></td><td>1.3</td><td>0.1</td><td></td></tr>
<tr><td><code>WP_W2</code></td><td>0.55</td><td>0.01</td><td></td></tr>
<tr><td><code>WP_HX</code></td><td>7</td><td>1</td><td></td></tr>
<tr><td><code>WP_HY</code></td><td>-24</td><td>5</td><td></td></tr>
</tbody></table></section>
<section class="grp" id="enemies"><h2>Enemies <small>(24)</small></h2>
<table><thead><tr><th>Variable</th><th>Default</th><th>Step</th><th>What it does</th></tr></thead><tbody>
<tr><td><code>SPEED_SNAKE</code></td><td>0.25</td><td>0.01</td><td></td></tr>
<tr><td><code>SPEED_BAT</code></td><td>0.35</td><td>0.01</td><td>flying</td></tr>
<tr><td><code>SPEED_CROCODILE</code></td><td>0.15</td><td>0.01</td><td></td></tr>
<tr><td><code>SPEED_RAPTOR</code></td><td>0.45</td><td>0.01</td><td></td></tr>
<tr><td><code>SPEED_LIZARDMAN</code></td><td>0.18</td><td>0.01</td><td></td></tr>
<tr><td><code>SPEED_SPIDER</code></td><td>0.3</td><td>0.01</td><td></td></tr>
<tr><td><code>SPEED_DRAGONFLY</code></td><td>0.5</td><td>0.01</td><td>flying</td></tr>
<tr><td><code>SPEED_BEAST</code></td><td>0.14</td><td>0.01</td><td></td></tr>
<tr><td><code>SPEED_SKELETON</code></td><td>0.22</td><td>0.01</td><td></td></tr>
<tr><td><code>BAT_BOB_PERIOD</code></td><td>16</td><td>1</td><td>the bat flies up and down: bigger = slower</td></tr>
<tr><td><code>BAT_BOB_HEIGHT</code></td><td>8</td><td>1</td><td>... and this high (units)</td></tr>
<tr><td><code>DRAGONFLY_BOB_PERIOD</code></td><td>9</td><td>1</td><td></td></tr>
<tr><td><code>DRAGONFLY_BOB_HEIGHT</code></td><td>12</td><td>1</td><td></td></tr>
<tr><td><code>ENEMY_RESPAWN_TICKS</code></td><td>18000</td><td>50</td><td>a killed enemy comes back after this many ticks (18000 = 5 minutes) - but only when you are more than 220 units away</td></tr>
<tr><td><code>NEVER_RESPAWN</code></td><td>1000000000000</td><td>50</td><td>the gorilla and the woman boss use this: they never come back</td></tr>
<tr><td><code>ATK_ON</code></td><td>1</td><td>1</td><td>1 = enemies play their attack animation, 0 = off.</td></tr>
<tr><td><code>ATK_T</code></td><td>44</td><td>5</td><td>length of the attack animation in ticks.</td></tr>
<tr><td><code>ATK_CD</code></td><td>150</td><td>10</td><td>ticks between two attack animations.</td></tr>
<tr><td><code>ATK_RY</code></td><td>34</td><td>5</td><td>height tolerance for starting the attack.</td></tr>
<tr><td><code>SK_HIT</code></td><td>1</td><td>1</td><td>1 = the long sword really hurts (in the last 2 attack pictures), 0 = it is only a picture.</td></tr>
<tr><td><code>SK_REACH</code></td><td>44</td><td>5</td><td></td></tr>
<tr><td><code>SPK_ON</code></td><td>1</td><td>1</td><td></td></tr>
<tr><td><code>SPK_K</code></td><td>0.2</td><td>0.01</td><td></td></tr>
<tr><td><code>SPK_HIT</code></td><td>10</td><td>1</td><td></td></tr>
</tbody></table></section>
<section class="grp" id="archer-10"><h2>Archer 10 <small>(18)</small></h2>
<table><thead><tr><th>Variable</th><th>Default</th><th>Step</th><th>What it does</th></tr></thead><tbody>
<tr><td><code>ARR_VOL</code></td><td>1</td><td>1</td><td></td></tr>
<tr><td><code>ARC_ON</code></td><td>1</td><td>1</td><td></td></tr>
<tr><td><code>ARC_HP</code></td><td>4</td><td>1</td><td>hits to kill her (machete, whip or throwing knives each count 1)</td></tr>
<tr><td><code>ARC_IDLE_LOOPS</code></td><td>3</td><td>1</td><td>she plays her idle animation this many times, then does ONE attack (shoots one arrow), then idle again ... (replaces the old fixed time between arr...</td></tr>
<tr><td><code>ARC_IDLE_TPF</code></td><td>4</td><td>1</td><td>ticks per idle picture (12 pictures: 4 -&gt; one idle loop = 48 ticks = 0.8 s, 3 loops = 2.4 s)</td></tr>
<tr><td><code>ARC_FADE</code></td><td>3</td><td>1</td><td>idle -&gt; attack: the first attack pictures fade in over this many pictures (0 = hard cut)</td></tr>
<tr><td><code>ARC_TPF</code></td><td>3.6</td><td>0.1</td><td>ticks per attack picture (25 pictures). Draw+shoot takes 25*3.6 = 90 ticks</td></tr>
<tr><td><code>ARC_REL</code></td><td>22</td><td>5</td><td>picture at which the arrow leaves the bow (the game spawns the real arrow there)</td></tr>
<tr><td><code>ARC_RECOV</code></td><td>16</td><td>1</td><td></td></tr>
<tr><td><code>ARC_RANGE</code></td><td>175</td><td>10</td><td>she starts shooting when you are closer than this many units</td></tr>
<tr><td><code>ARC_SPEED</code></td><td>1.5</td><td>0.1</td><td>arrow speed (units/tick). ARC_AIM = .3 how steeply she may aim up/down</td></tr>
<tr><td><code>ARC_AIM</code></td><td>0.3</td><td>0.01</td><td></td></tr>
<tr><td><code>ARC_LEN</code></td><td>21</td><td>5</td><td>drawn arrow length. ARC_K = .1548, ARC_AX/ARC_AY = size / feet anchor of her pictures</td></tr>
<tr><td><code>ARC_K</code></td><td>0.1703</td><td>0.01</td><td></td></tr>
<tr><td><code>ARC_AX</code></td><td>156</td><td>10</td><td></td></tr>
<tr><td><code>ARC_AY</code></td><td>316</td><td>10</td><td></td></tr>
<tr><td><code>ARC_SX</code></td><td>13.5</td><td>1</td><td></td></tr>
<tr><td><code>ARC_SY</code></td><td>45.4</td><td>1</td><td></td></tr>
</tbody></table></section>
<section class="grp" id="archer-30"><h2>Archer 30 <small>(18)</small></h2>
<table><thead><tr><th>Variable</th><th>Default</th><th>Step</th><th>What it does</th></tr></thead><tbody>
<tr><td><code>ARC2_ON</code></td><td>1</td><td>1</td><td>1 = she shoots, 0 = she only stands.</td></tr>
<tr><td><code>ARC2_HP</code></td><td>2</td><td>1</td><td>hits to kill her.</td></tr>
<tr><td><code>ARC2_PERIOD</code></td><td>300</td><td>10</td><td>ticks between two shots (5 s).</td></tr>
<tr><td><code>ARC2_RANGE</code></td><td>175</td><td>10</td><td>she starts shooting closer than this.</td></tr>
<tr><td><code>ARC2_SPEED</code></td><td>1.6</td><td>0.1</td><td>arrow speed.</td></tr>
<tr><td><code>ARC2_AIM</code></td><td>0.8</td><td>0.01</td><td>how steeply she may aim up/down (was .3 = arrows went straight past you when you stood higher or lower).</td></tr>
<tr><td><code>ARC2_LEN</code></td><td>24</td><td>5</td><td>arrow length (units).</td></tr>
<tr><td><code>ARC2_THICK</code></td><td>1.7</td><td>0.1</td><td>arrow thickness (1 = as drawn).</td></tr>
<tr><td><code>ARC2_K</code></td><td>0.129</td><td>0.01</td><td>size of the picture (bigger = taller girl).</td></tr>
<tr><td><code>ARC2_AX</code></td><td>102</td><td>10</td><td></td></tr>
<tr><td><code>ARC2_AY</code></td><td>374</td><td>10</td><td></td></tr>
<tr><td><code>ARC2_SX</code></td><td>9</td><td>1</td><td></td></tr>
<tr><td><code>ARC2_SY</code></td><td>43</td><td>5</td><td></td></tr>
<tr><td><code>ARC2_BX</code></td><td>138</td><td>10</td><td></td></tr>
<tr><td><code>ARC2_BY</code></td><td>440</td><td>10</td><td></td></tr>
<tr><td><code>ARC2_REC</code></td><td>20</td><td>1</td><td></td></tr>
<tr><td><code>ARC2_SCORE</code></td><td>250</td><td>10</td><td>points for a kill.</td></tr>
<tr><td><code>ARC2_IT</code></td><td>40</td><td>5</td><td></td></tr>
</tbody></table></section>
<section class="grp" id="gorilla"><h2>Gorilla <small>(23)</small></h2>
<table><thead><tr><th>Variable</th><th>Default</th><th>Step</th><th>What it does</th></tr></thead><tbody>
<tr><td><code>GOR_ON</code></td><td>1</td><td>1</td><td></td></tr>
<tr><td><code>GOR_HP</code></td><td>6</td><td>1</td><td>hits to kill</td></tr>
<tr><td><code>GOR_REACH</code></td><td>137.5</td><td>10</td><td>longest jump (units; was 125, now 10% wider)</td></tr>
<tr><td><code>GOR_JMIN</code></td><td>3</td><td>1</td><td></td></tr>
<tr><td><code>GOR_JMAX</code></td><td>7</td><td>1</td><td>a visible gorilla hops 3 to 7 metres per jump (1 m = GOR_M units)</td></tr>
<tr><td><code>GOR_CATCH</code></td><td>5</td><td>1</td><td>OFF screen he runs this many times faster and jumps GOR_REACH far, so he always catches up with you</td></tr>
<tr><td><code>GOR_STUCK</code></td><td>90</td><td>5</td><td>off screen and no way forward (hole, wall) for this many ticks: he appears again on the ground behind you</td></tr>
<tr><td><code>GOR_ARC</code></td><td>44.9</td><td>1</td><td>jump height (was 34, then 37.4, now +20% more)</td></tr>
<tr><td><code>GOR_UP</code></td><td>26</td><td>5</td><td>highest step he can jump up</td></tr>
<tr><td><code>GOR_DROP</code></td><td>90</td><td>5</td><td>deepest drop he jumps down</td></tr>
<tr><td><code>GOR_WATER</code></td><td>205</td><td>10</td><td>ground lower than this is water</td></tr>
<tr><td><code>GOR_TPF</code></td><td>6</td><td>1</td><td>ticks per attack picture (jump speed; was 2.4, then 3, now half the speed again)</td></tr>
<tr><td><code>GOR_F0</code></td><td>8</td><td>1</td><td></td></tr>
<tr><td><code>GOR_FT</code></td><td>17</td><td>1</td><td></td></tr>
<tr><td><code>GOR_FL</code></td><td>28</td><td>5</td><td></td></tr>
<tr><td><code>GOR_REC</code></td><td>68</td><td>5</td><td></td></tr>
<tr><td><code>GOR_CD</code></td><td>68</td><td>5</td><td>rest between jumps (ticks, was 34)</td></tr>
<tr><td><code>GOR_STOMP</code></td><td>26</td><td>5</td><td>landing damage radius</td></tr>
<tr><td><code>GOR_K</code></td><td>0.192</td><td>0.01</td><td>size (units per picture pixel)</td></tr>
<tr><td><code>GOR_AAX</code></td><td>170</td><td>10</td><td></td></tr>
<tr><td><code>GOR_AAY</code></td><td>287.5</td><td>10</td><td></td></tr>
<tr><td><code>GOR_IAX</code></td><td>101.55</td><td>10</td><td></td></tr>
<tr><td><code>GOR_IAY</code></td><td>338.5</td><td>10</td><td></td></tr>
</tbody></table></section>
<section class="grp" id="woman-boss"><h2>Woman Boss <small>(18)</small></h2>
<table><thead><tr><th>Variable</th><th>Default</th><th>Step</th><th>What it does</th></tr></thead><tbody>
<tr><td><code>WBS_VOL</code></td><td>1</td><td>1</td><td></td></tr>
<tr><td><code>BOSS_FIRE_TICKS</code></td><td>120</td><td>10</td><td>ticks between two shots (120 = one shot every 2 seconds). Higher = easier.</td></tr>
<tr><td><code>BOSS_BULLET_SPEED</code></td><td>1.3</td><td>0.1</td><td>speed of the bullets (was 2.3). Lower = easier.</td></tr>
<tr><td><code>BOSS_WALK_TPF</code> <span class="new">new</span></td><td>2.8</td><td>0.1</td><td>end boss walk: ticks per picture (bigger = slower legs)</td></tr>
<tr><td><code>WB_ON</code></td><td>1</td><td>1</td><td></td></tr>
<tr><td><code>WB_HP</code></td><td>8</td><td>1</td><td>end boss hp:12 (+ hp0:12, in bossInit)</td></tr>
<tr><td><code>WB_PERIOD</code></td><td>120</td><td>10</td><td>ticks between shots (120 = every 2 seconds)</td></tr>
<tr><td><code>WB_TPF</code></td><td>5</td><td>1</td><td>ticks per attack picture (draw + aim + shoot = 50 ticks)</td></tr>
<tr><td><code>WB_RANGE</code></td><td>230</td><td>10</td><td>she starts shooting when you are closer than this</td></tr>
<tr><td><code>WB_SPEED</code></td><td>2.6</td><td>0.1</td><td>bullet speed</td></tr>
<tr><td><code>WB_AIM</code></td><td>0.18</td><td>0.01</td><td></td></tr>
<tr><td><code>WB_REL</code></td><td>5</td><td>1</td><td></td></tr>
<tr><td><code>WB_IT</code></td><td>7</td><td>1</td><td></td></tr>
<tr><td><code>WB_K</code></td><td>0.1735</td><td>0.01</td><td>size WB_MX / WB_MY = muzzle position (35 / 40.6 units from her feet)</td></tr>
<tr><td><code>WB_AX</code></td><td>259</td><td>10</td><td></td></tr>
<tr><td><code>WB_AY</code></td><td>308</td><td>10</td><td></td></tr>
<tr><td><code>WB_MX</code></td><td>35</td><td>5</td><td></td></tr>
<tr><td><code>WB_MY</code></td><td>40.6</td><td>1</td><td></td></tr>
</tbody></table></section>
<section class="grp" id="screen-misc"><h2>Screen / Misc <small>(9)</small></h2>
<table><thead><tr><th>Variable</th><th>Default</th><th>Step</th><th>What it does</th></tr></thead><tbody>
<tr><td><code>DANCE_SECONDS</code> <span class="new">new</span></td><td>5</td><td>0.5</td><td>seconds the win dance picture is shown before the win screen (space / enter / click skips it)</td></tr>
<tr><td><code>CHEAT_KEYS</code></td><td>1</td><td>1</td><td>1 = test keys work while playing (5 = in front of an enemy 10 archer, 8 = enemy 30 archer, 7 = end boss, 6 = chimp, 0 = skeleton bridge, 9 = skip t...</td></tr>
<tr><td><code>CRAWL_K</code></td><td>4.8</td><td>0.1</td><td>crawl animation speed: pictures per step of walking. Bigger = faster legs.</td></tr>
<tr><td><code>BR_ANCH</code></td><td>0.76</td><td>0.01</td><td>share of the bridge picture above the walking line (bigger = bridge sits higher,</td></tr>
<tr><td><code>CL_ON</code></td><td>1</td><td>1</td><td></td></tr>
<tr><td><code>CL_ALPHA</code></td><td>0.2</td><td>0.01</td><td></td></tr>
<tr><td><code>CL_SPAN</code></td><td>420</td><td>10</td><td></td></tr>
<tr><td><code>CL_DRIFT</code></td><td>0.03</td><td>0.001</td><td></td></tr>
<tr><td><code>CL_Y</code></td><td>34</td><td>5</td><td>height above the highest palm crown of the level (bigger = higher in the sky)</td></tr>
</tbody></table></section>
<section class="grp" id="chimp"><h2>Chimp <small>(17)</small></h2>
<table><thead><tr><th>Variable</th><th>Default</th><th>Step</th><th>What it does</th></tr></thead><tbody>
<tr><td><code>CHAT_VOL</code></td><td>0.8</td><td>0.01</td><td></td></tr>
<tr><td><code>CHM_ON</code></td><td>1</td><td>1</td><td></td></tr>
<tr><td><code>CHM_HP</code></td><td>2</td><td>1</td><td>hits to kill him</td></tr>
<tr><td><code>CHM_PERIOD</code></td><td>300</td><td>10</td><td>ticks from one throw to the next (5 s)</td></tr>
<tr><td><code>CHM_RANGE</code></td><td>150</td><td>10</td><td>he throws when you are closer than this (units)</td></tr>
<tr><td><code>CHM_TPF</code></td><td>3.4</td><td>0.1</td><td>ticks per throw picture</td></tr>
<tr><td><code>CHM_ITPF</code></td><td>2.4</td><td>0.1</td><td>ticks per idle picture</td></tr>
<tr><td><code>CHM_REL</code></td><td>9</td><td>1</td><td>throw picture where the coconut leaves his hand</td></tr>
<tr><td><code>CHM_FLY</code></td><td>1.7</td><td>0.1</td><td>coconut speed (units per tick), CHM_GRAV = .05 gravity</td></tr>
<tr><td><code>CHM_GRAV</code></td><td>0.05</td><td>0.001</td><td></td></tr>
<tr><td><code>CHM_K</code></td><td>0.19</td><td>0.01</td><td>picture size (units per picture pixel)</td></tr>
<tr><td><code>CHM_BODY</code></td><td>11.5</td><td>1</td><td>how far his body hangs beside the vine</td></tr>
<tr><td><code>CHM_LIFT</code></td><td>26</td><td>5</td><td>height of his hit box above the ground</td></tr>
<tr><td><code>CHM_TOPY</code></td><td>16.3</td><td>1</td><td></td></tr>
<tr><td><code>CHM_ROPE</code></td><td>130</td><td>10</td><td>rope length above him</td></tr>
<tr><td><code>CHM_W</code></td><td>226</td><td>10</td><td></td></tr>
<tr><td><code>CHM_H</code></td><td>294</td><td>10</td><td></td></tr>
</tbody></table></section>
<section class="grp" id="princess-dance"><h2>Princess / Dance <small>(21)</small></h2>
<table><thead><tr><th>Variable</th><th>Default</th><th>Step</th><th>What it does</th></tr></thead><tbody>
<tr><td><code>DANCE_SCALE</code></td><td>1.2</td><td>0.1</td><td>size of the victory dance (1 = same height as the idle pose)</td></tr>
<tr><td><code>PIL_H</code></td><td>70</td><td>5</td><td></td></tr>
<tr><td><code>DANCE_ON</code></td><td>1</td><td>1</td><td>1 = the dance plays after the boss, 0 = no dance.</td></tr>
<tr><td><code>DANCE_TPF</code></td><td>2.5</td><td>0.1</td><td>ticks per picture (2.5 = the video&#x27;s 24 pictures per second).</td></tr>
<tr><td><code>DANCE_LOOPS</code></td><td>3</td><td>1</td><td>how many times the dance is played.</td></tr>
<tr><td><code>PR_ON</code></td><td>1</td><td>1</td><td></td></tr>
<tr><td><code>PR_K</code></td><td>0.1985</td><td>0.01</td><td>size (units per picture pixel; the hero&#x27;s dance is about .2)</td></tr>
<tr><td><code>PR_X</code></td><td>18041</td><td>50</td><td></td></tr>
<tr><td><code>PR_FY</code></td><td>129.5</td><td>10</td><td>where she stands (centre x / feet y)</td></tr>
<tr><td><code>PR_DX</code></td><td>42</td><td>5</td><td>distance between the two dancers</td></tr>
<tr><td><code>CAP_ON</code></td><td>1</td><td>1</td><td></td></tr>
<tr><td><code>CAP_X</code></td><td>17862</td><td>50</td><td></td></tr>
<tr><td><code>CAP_FY</code></td><td>176</td><td>10</td><td></td></tr>
<tr><td><code>CAP_K</code></td><td>0.165</td><td>0.01</td><td></td></tr>
<tr><td><code>CAP_TPF</code></td><td>6</td><td>1</td><td></td></tr>
<tr><td><code>CAP_ALPHA</code></td><td>1</td><td>1</td><td></td></tr>
<tr><td><code>CAP_VOL</code></td><td>1</td><td>1</td><td>volume of the scene&#x27;s sound (audio/captive_scene.mp3), played once at the start of every loop of the animation. 0 = silent</td></tr>
<tr><td><code>PRH_ON</code></td><td>1</td><td>1</td><td></td></tr>
<tr><td><code>PRH_X</code></td><td>18028.6</td><td>1000</td><td></td></tr>
<tr><td><code>PRH_FY</code></td><td>131.9</td><td>10</td><td></td></tr>
<tr><td><code>PRH_K</code></td><td>0.13196</td><td>0.01</td><td></td></tr>
</tbody></table></section>
<section class="grp" id="red-gems"><h2>Red Gems <small>(3)</small></h2>
<table><thead><tr><th>Variable</th><th>Default</th><th>Step</th><th>What it does</th></tr></thead><tbody>
<tr><td><code>RED_GEMS_ON</code></td><td>1</td><td>1</td><td></td></tr>
<tr><td><code>RED_GEM_DAMAGE</code></td><td>1</td><td>1</td><td>hearts lost when she touches a red gem</td></tr>
<tr><td><code>RED_GEM_HIT</code></td><td>6</td><td>1</td><td>half size of the dangerous part (units) around the gem centre</td></tr>
</tbody></table></section>
<section class="grp" id="animation-frames"><h2>Animation Frames <small>(43)</small></h2>
<table><thead><tr><th>Variable</th><th>Default</th><th>Step</th><th>What it does</th></tr></thead><tbody>
<tr><td><code>FRAMES_SNAKE_MOVE</code></td><td>4</td><td>1</td><td>number of pictures of the animation &quot;snake move&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_SNAKE_ATTACK</code></td><td>4</td><td>1</td><td>number of pictures of the animation &quot;snake attack&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_BAT_FLY</code></td><td>4</td><td>1</td><td>number of pictures of the animation &quot;bat fly&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_BAT_ATTACK</code></td><td>4</td><td>1</td><td>number of pictures of the animation &quot;bat attack&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_CROCODILE_SWIM</code></td><td>4</td><td>1</td><td>number of pictures of the animation &quot;crocodile swim&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_CROCODILE_ATTACK</code></td><td>4</td><td>1</td><td>number of pictures of the animation &quot;crocodile attack&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_RAPTOR_RUN</code></td><td>4</td><td>1</td><td>number of pictures of the animation &quot;raptor run&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_RAPTOR_ATTACK</code></td><td>4</td><td>1</td><td>number of pictures of the animation &quot;raptor attack&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_LIZARDMAN_WALK</code></td><td>4</td><td>1</td><td>number of pictures of the animation &quot;lizardman walk&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_LIZARDMAN_ATTACK</code></td><td>4</td><td>1</td><td>number of pictures of the animation &quot;lizardman attack&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_SPIDER_WALK</code></td><td>4</td><td>1</td><td>number of pictures of the animation &quot;spider walk&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_SPIDER_ATTACK</code></td><td>4</td><td>1</td><td>number of pictures of the animation &quot;spider attack&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_DRAGONFLY_FLY</code></td><td>4</td><td>1</td><td>number of pictures of the animation &quot;dragonfly fly&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_DRAGONFLY_ATTACK</code></td><td>4</td><td>1</td><td>number of pictures of the animation &quot;dragonfly attack&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_BEAST_WALK</code></td><td>4</td><td>1</td><td>number of pictures of the animation &quot;beast walk&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_BEAST_ATTACK</code></td><td>4</td><td>1</td><td>number of pictures of the animation &quot;beast attack&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_SKELETON_WALK</code></td><td>36</td><td>1</td><td>number of pictures of the animation &quot;skeleton walk&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_SKELETON_ATTACK</code></td><td>4</td><td>1</td><td>number of pictures of the animation &quot;skeleton attack&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_BOSS_WALK</code> <span class="new">new</span></td><td>81</td><td>1</td><td>number of pictures of the animation &quot;end boss walk&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_CAPTIVE</code></td><td>17</td><td>1</td><td>number of pictures of the animation &quot;captive&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_ARCHER10_IDLE</code></td><td>12</td><td>1</td><td>number of pictures of the animation &quot;archer10 idle&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_ARCHER10_ATTACK</code></td><td>25</td><td>1</td><td>number of pictures of the animation &quot;archer10 attack&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_ARCHER30_IDLE</code></td><td>17</td><td>1</td><td>number of pictures of the animation &quot;archer30 idle&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_ARCHER30_ATTACK</code></td><td>39</td><td>1</td><td>number of pictures of the animation &quot;archer30 attack&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_GORILLA_ATTACK</code></td><td>30</td><td>1</td><td>number of pictures of the animation &quot;gorilla attack&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_GORILLA_IDLE</code></td><td>2</td><td>1</td><td>number of pictures of the animation &quot;gorilla idle&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_WOMANBOSS_ATTACK</code></td><td>6</td><td>1</td><td>number of pictures of the animation &quot;womanboss attack&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_WOMANBOSS_IDLE</code></td><td>7</td><td>1</td><td>number of pictures of the animation &quot;womanboss idle&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_CHIMP_HANG</code></td><td>48</td><td>1</td><td>number of pictures of the animation &quot;chimp hang&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_CHIMP_THROW</code></td><td>12</td><td>1</td><td>number of pictures of the animation &quot;chimp throw&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_HERO_SWIM</code></td><td>11</td><td>1</td><td>number of pictures of the animation &quot;hero swim&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_HERO_HANG</code></td><td>21</td><td>1</td><td>number of pictures of the animation &quot;hero hang&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_HERO_JUMP</code></td><td>45</td><td>1</td><td>number of pictures of the animation &quot;hero jump&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_HERO_WHIP_ATTACK</code></td><td>11</td><td>1</td><td>number of pictures of the animation &quot;hero whip attack&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_HERO_CROUCH_DOWN</code></td><td>5</td><td>1</td><td>number of pictures of the animation &quot;hero crouch down&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_HERO_CLIMB</code></td><td>33</td><td>1</td><td>number of pictures of the animation &quot;hero climb&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_HERO_SWING_LEAP</code></td><td>19</td><td>1</td><td>number of pictures of the animation &quot;hero swing leap&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_CLOUDS</code></td><td>5</td><td>1</td><td>number of pictures of the animation &quot;clouds&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_PRINCESS_DANCE</code></td><td>82</td><td>1</td><td>number of pictures of the animation &quot;princess dance&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_HERO_IDLE</code></td><td>6</td><td>1</td><td>number of pictures of the animation &quot;hero idle&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_HERO_ROPE_HANG</code></td><td>37</td><td>1</td><td>number of pictures of the animation &quot;hero rope hang&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_HERO_CRAWL</code></td><td>45</td><td>1</td><td>number of pictures of the animation &quot;hero crawl&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
<tr><td><code>FRAMES_HERO_DANCE</code></td><td>90</td><td>1</td><td>number of pictures of the animation &quot;hero dance&quot; (the numbered files in the graphics folder). Needs a page reload (F5).</td></tr>
</tbody></table></section>
</div>
</main>
<script>
(function(){
  var q=document.getElementById('q');
  q.addEventListener('input',function(){
    var t=q.value.trim().toLowerCase();
    document.querySelectorAll('section.grp').forEach(function(s){
      var any=false;
      s.querySelectorAll('tbody tr').forEach(function(r){
        var m=!t||r.textContent.toLowerCase().indexOf(t)>-1;
        r.classList.toggle('hide',!m); if(m)any=true;
      });
      s.classList.toggle('hide',!any);
    });
  });
}());
</script>
</body>

