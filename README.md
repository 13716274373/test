# 查询账户信息
# -*- encoding=utf8 -*-
__author__ = "apple"

from airtest.core.api import *

from selenium import webdriver
from selenium.webdriver.common.keys import Keys
from airtest_selenium.proxy import WebChrome
from selenium.webdriver.common.by import By
import time
driver = WebChrome()
driver.implicitly_wait(20)
driver.get("http://49.232.26.196:7326/webmgr5/main.html")#管理器地址
driver.find_element_by_xpath("//*[@id=\"_easyui_tree_15\"]/span[4]").click()#点击左侧列表栏
iframe=driver.find_element_by_xpath('//*[@id="main_tabs"]/div[2]/div/div/iframe')  #找到iframe这个房间
driver.switch_to_frame(iframe)  #进入iframe房间
driver.find_element_by_xpath('//*[@id="userId"]').send_keys('107340') #操作房间里的元素
time.sleep(3)#延时3s
driver.find_element_by_xpath("/html/body/table/tbody/tr[1]/td[3]/button[1]").click()#点击按钮查询账号信息
auto_setup(__file__)
