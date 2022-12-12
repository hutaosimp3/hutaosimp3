@@ -1,6 +1,6 @@
MIT License

Авторское право (c) 2021 Колин Хартиган
Авторское право (c) 2022 Колин Хартиган

Настоящим разрешение предоставляется бесплатно любому лицу, получившему копию
этого программного обеспечения и связанных с ним файлов документации ("Программное обеспечение"), для решения
  2 
. client/src/components/buddies/Buddies.js
@@ -164,7 +164,7 @@ функциональные приятели (реквизит) {
                    />
                </div>

                width{ {=style div <: "авто", height: "100%", marginLeft: "10px", display: "гибкий", flexDirection: "строка", justifyContent: "гибкий", alignItems: "центр" }}>
                width{ {=стиль div <: " авто",высота : "60 пикселей", левый край: "10 пикселей",  отображение: "гибкий",  flexDirection: "строка",  выравнивание содержимого: "гибкий",  выравнивание элементов: "по центру" }}>
                    margin{ {=style } })true (Избранное все{=>) ( { =onClick"вторичный"= отключение цвета  "содержащийся"=кнопка варианта  <: "5 пикселей" }}>Избранное все</Button>
                    margin{ {=style } })false (избранное все{=>) ( { =onClick"вторичный"=  отключение цвета  "содержащийся"=кнопка варианта  <: "5 пикселей" }}>Неблагоприятно для всех</Button>
                </div>
  46  
client/src/components/collection/Collection.js
@@ -59,31 +59,37 @@ Коллекция функций (реквизит) {
            Маленькое окно!{ ?
                (
                    <>
                        null!==loadout. props { ? <SkinChanger  warning skinsOwned={props.skinsOwned}/> : null}
                        <Имя_класса сетки ={classes.root} стиль={props.style} оправдание контейнера ="центр" направление ="строка" Выравнивание элементов ="центр" интервал ={3}>
                            {loadoutGridOrder.map(строка => {
                                если (props.loadout !== null) {
                                    return (
                                        row.map(data => {
                                            if (data.type === "weapon") {
                                                return <Grid className={classes.collectionItem} item key={data.uuid} md={data.sidearm === true ? 2 : 3} sm={12} xs={12}><Weapon data={props.loadout[data.uuid]} uuid={data.uuid} displayName={data.displayName} useLargeWeaponImage={useLargeWeaponImage} weaponEditorCallback={props.weaponEditorCallback} isSidearm={data.sidearm} /></Grid>
                                            }
                                            else {
                                                return (<Grid key="placeholder" className={classes.collectionItem} item md={6} sm={false} xs={false} />);
                                            }
                                        })
                                    )
                                } else {
                                    return null;
                                }
                            })}
                        </Grid>
                        {props.loadout !== null ? <SkinChangerWarning skinsOwned={props.skinsOwned} /> : null}

                        <div style={{ width: "100%", height: "100%", display: "flex", flexDirection: "column", justifyContent: "center", alignItems: "center" }}>
                            {/* <div style={{ width: "100%", height: "50px", display: "flex", flexDirection: "row", justifyContent: "flex-start", alignItems: "center" }}>
                                hello
                            </div> */}
                            <Grid className={classes.root} style={props.style} container justifyContent="center" direction="row" alignItems="center" spacing={3}>
                                {loadoutGridOrder.map(row => {
                                    if (props.loadout !== null) {
                                        return (
                                            row.map(data => {
                                                if (data.type === "weapon") {
                                                    return <Grid className={classes.collectionItem} item key={data.uuid} md={data.sidearm === true ? 2 : 3} sm={12} xs={12}><Weapon data={props.loadout[data.uuid]} uuid={data.uuid} displayName={data.displayName} useLargeWeaponImage={useLargeWeaponImage} weaponEditorCallback={props.weaponEditorCallback} isSidearm={data.sidearm} /></Grid>
                                                }
                                                else {
                                                    return (<Grid key="placeholder" className={classes.collectionItem} item md={6} sm={false} xs={false} />);
                                                }
                                            })
                                        )
                                    } else {
                                        return null;
                                    }
                                })}
                            </Grid>
                        </div>
                    </>
                ) : (
                    <div style={{ display: "flex", flexDirection: "column", alignItems: "center", justifyContent: "center", width: "100%", height: "100%" }}>
                        <AspectRatio style={{ fontSize: 60 }} />
                        <Typography variant="h6" style={{ marginTop: "10px", textAlign: "center" }}>
                            Make your window bigger for this page to work properly
                            Make your window larger for this page to work properly
                        </Typography>
                    </div>
                )
  2  
client/src/components/collection/sub/WeaponCollectionItem.js
@@ -304,7 +304,7 @@ function Weapon(props) {
                            </Collapse>
                        </div>
                    </div>
                    <Grow in>
                    <Grow in={!isUpdatingBuddy}>
                        <div className={classes.buddyContainer} style={{ width: props.isSidearm ? "20%" : "14%" }}>
                            {props.uuid !== "2f59173c-4bed-b6c3-2191-dea9b58be9c7" ?
                                <img alt={skinData.buddy_name} className={classes.buddyImage} src={skinData.buddy_image !== "" ? skinData.buddy_image : null} />
  12  
client/src/pages/About.js
@@ -111,13 +111,13 @@ function About(props) {
                                VALORANT's client API were instrumental in VIM's development.
                            </Typography>
                        </div>
                        <Divider style={{margin: "15px 0px"}} />
                        <Divider style={{ margin: "15px 0px" }} />
                        <div className={classes.section} style={{ marginBottom: "10px", }}>
                            <Typography variant="h3" style={{ color: "white", fontSize: "2rem", marginBottom: "10px", }}>License</Typography>
                            <Typography variant="body1" style={{ lineHeight: ".5em", width: "95%", marginLeft: "1%" }}>
                                <p>MIT License</p>
                                <br />
                                <p>Copyright (c) 2021 Colin Hartigan</p>
                                <p>Copyright (c) 2022 Colin Hartigan</p>
                                <br />
                                <p>Permission is hereby granted, free of charge, to any person obtaining a copy</p>
                                <p>of this software and associated documentation files (the "Software"), to deal</p>
@@ -139,6 +139,14 @@ function About(props) {
                            </Typography>
                        </div>

                        <div className={classes.section} style={{ marginBottom: "10px", }}>
                            <Typography variant="h3" style={{ color: "white", fontSize: "2rem", marginBottom: "10px", }}>Legal (Riot's Jibber Jabber)</Typography>
                            <Typography variant="body1" style={{ lineHeight: ".5em", width: "95%", marginLeft: "1%" }}>
                                <p>This project is not affiliated with Riot Games or any of its employees and therefore does not reflect the views of said parties. This is purely a fan-made project to enhance VALORANT's inventory management.</p>
                                <p>Riot Games does not endorse or sponsor this project. Riot Games, and all associated properties are trademarks or registered trademarks of Riot Games, Inc.</p>
                            </Typography>
                        </div>

                        <div className={classes.section}>
                            <Typography variant="h3" style={{ color: "white", fontSize: "2rem", marginBottom: "10px", }}>Third-party software</Typography>
                            <Typography variant="body1">
  2  
client/src/pages/CollectionHome.js
@@ -98,7 +98,7 @@ function CollectionHome(props) {
            {inventory.skins !== {} ?
                <Container maxWidth={false} style={{ display: "flex", height: "auto", flexGrow: 1, }}>
                    {weaponEditor}
                    <Collection style={{ padding: "20px 0px 20px 0px" }} weaponEditorCallback={modificationMenu} loadout={loadout} setLoadout={null} skinsOwned={uniqueSkinsOwned} />
                    <Collection style={{ padding: "10px 0px 10px 0px" }} weaponEditorCallback={modificationMenu} loadout={loadout} setLoadout={null} skinsOwned={uniqueSkinsOwned} />
                </Container>
                : null}
        </div>
  18  
server/src/client_config.py
@@ -1,18 +1,18 @@
from valclient import Client

# version
SERVER_VERSION = "1.1.0b1"
SERVER_VERSION = "1.1.0"

# debug settings
IS_TEST_BUILD = True # directs to the test client website
IS_TEST_BUILD = False # directs to the test client website

DEBUG = False # prints all log messages to console

FORCE_DEFAULT_SKINS = False # only deafult skins unlocked
UNLOCK_ALL_SKINS = False # just for testing purposes, doesn't actually unlock anything
UNLOCK_ALL_BUDDIES = False # just for testing purposes, doesn't actually unlock anything

USE_TEST_DIRECTORY = True # use a different directory for testing purposes
USE_TEST_DIRECTORY = False # use a different directory for testing purposes
AUTH_MODE = "local" # local or credentials
CLIENT_STATE_REFRESH_INTERVAL = 5

@@ -79,4 +79,16 @@
            }
        }
    },
    "buddy_randomizer": {
        "type": "section",
        "display": "Buddy Randomizer Settings",
        "settings": {
            "auto_skin_randomize": {
                "type": "bool",
                "display": "Automatically randomize buddies",
                "description": "Automatically randomize favorite buddies after a match ends.",
                "value": True,
            },
        }
    }
}
  11  
server/src/inventory_management/buddy_manager.py
@@ -35,6 +35,7 @@ async def update_inventory(**kwargs):
                inventory[uuid] = new_data
                break


        File_Manager.update_individual_inventory(inventory, "buddies")
        await shared.client.broadcast_loadout()

@@ -125,6 +126,16 @@ def update_buddy_database():
                        "locked_weapon_display_name": existing_buddy_data["instances"][instance]["locked_weapon_display_name"] if existing_buddy_data is not None else "",
                    }

                # check for invalid favorite/lock combinations
                for instance in buddy_payload["instances"].values():
                    if instance["locked"]:
                        instance["favorite"] = False
                        if instance["locked_weapon_uuid"] == "" or instance["locked_weapon_display_name"] == "":
                            instance["locked"] = False
                            instance["locked_weapon_uuid"] = ""
                            instance["locked_weapon_display_name"] = ""


                inventory[buddy["uuid"]] = buddy_payload

        sort = sorted(inventory.items(), key=lambda x: x[1]["display_name"].lower())
  13  
server/src/session_management/client_state.py
@@ -1,6 +1,7 @@
import asyncio, traceback, json, logging

from ..randomizers.skin_randomizer import Skin_Randomizer
from ..randomizers.buddy_randomizer import Buddy_Randomizer
from ..sys_utilities.system import System
from ..broadcast import broadcast

@@ -26,9 +27,12 @@ def reset(self):
        shared.ingame = False
        self.inrange = False

    async def dispatch_randomizer(self):
    async def dispatch_randomizer(self, type):
        logger.debug("randomizing")
        await Skin_Randomizer.randomize()
        if type == "skins":
            await Skin_Randomizer.randomize()
        elif type == "buddies":
            await Buddy_Randomizer.randomize()

    async def randomizer_check(self):
        if self.presence is not None and self.presence != {}:
@@ -43,7 +47,10 @@ async def randomizer_check(self):
                            self.inrange = False
                            return 
                    else:
                        await self.dispatch_randomizer()
                        await self.dispatch_randomizer("skins")

                if shared.config["skin_randomizer"]["settings"]["auto_skin_randomize"]["value"] == True:
                    await self.dispatch_randomizer("buddies")


    async def check_presence(self):
