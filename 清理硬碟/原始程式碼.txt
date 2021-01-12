@echo off
color 0a
TITLE ：清理win10系統垃圾
echo 清理垃圾中，速度由電腦垃圾量大小而定
echo 請勿關閉本視窗。
echo 正在清除系統垃圾文件，請稍後......
echo 刪除更新備份目錄
RD %windir%\$hf_mig$ /Q /S
echo 把更新移除資料夾的名字保存成afan_09180918.txt
dir %windir%\$NtUninstall* /a:d /b >%windir%\afan_09180918.txt
echo 從afan_09180918.txt中讀取資料夾列表並且刪除資料夾
for /f %%i in (%windir%\afan_09180918.txt) do rd %windir%\%%i /s /q
echo 刪除afan_09180918.txt
del %windir%\afan_09180918.txt /f /q
echo 刪除安裝記錄內容
del %windir%\KB*.log /f /q
echo 刪除系統目錄下暫存檔案
del /f /s /q %systemdrive%\*.tmp
echo 刪除系統目錄下暫存檔案
del /f /s /q %systemdrive%\*._mp
echo 刪除系統目錄下記錄文件
del /f /s /q %systemdrive%\*.log
echo 刪除系統目錄下GID文件
del /f /s /q %systemdrive%\*.gid
echo 刪除系統目錄下硬碟掃描時所留下的檔案
del /f /s /q %systemdrive%\*.chk
echo 刪除系統目錄下old文件
del /f /s /q %systemdrive%\*.old
echo 刪除回收桶的無用文件
del /f /s /q %systemdrive%\recycled\*.*
echo 刪除系統目錄下備份文件
del /f /s /q %windir%\*.bak
echo 刪除應用程式暫存檔案
del /f /s /q %windir%\prefetch\*.*
echo 刪除系統維護等操作產生的暫存檔案
rd /s /q %windir%\temp md %windir%\temp
echo 刪除目前使用者的瀏覽記錄
del /f /q %userprofile%\cookies\*.*
echo 刪除網路臨時檔案
del /f /s /q "%userprofile%\local settings\temporary internet files\*.*"
echo 刪除當前用戶日常操作暫存檔案
del /f /s /q "%userprofile%\local settings\temp\*.*"
echo 刪除訪問記錄（開始選單中的裡面的東西）
del /f /s /q "%userprofile%\recent\*.*"
echo
echo 清除系統垃圾完成
echo
echo.