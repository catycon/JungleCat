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
