---
title: グローバル変数 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.variables
dev_langs:
- C++
helpviewer_keywords:
- global variables
- variables, global
- global variables, Microsoft run-time library
ms.assetid: 01d1551c-2f0c-4f72-935c-6442caccf84f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a2da3dd07c7088bee4be750b764b4a467bfebeae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="global-variables"></a>グローバル変数
Microsoft C ランタイム ライブラリには、次のグローバル変数またはマクロが用意されています。 これらのグローバル変数またはマクロの一部は、より安全かつ機能的なバージョンが優先されるため、非推奨とされました。グローバル変数の代わりにそれらを使用することをお勧めします。  
  
|変数|説明|  
|--------------|-----------------|  
|[__argc、\__argv、\__wargv](../c-runtime-library/argc-argv-wargv.md)|コマンド ライン引数を格納します。|  
|[_daylight、_dstbias、_timezone、and _tzname](../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)|非推奨。 代わりに、`_get_daylight`、`_get_dstbias`、`_get_timezone`、および `_get_tzname` を使用します。<br /><br /> 現地時刻に合わせます。一部の日付関数および時刻関数で使用されます。|  
|[errno、_doserrno、_sys_errlist、_sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)|非推奨。 代わりに、`_get_errno`、`_set_errno`、`_get_doserrno`、`_set_doserrno`、`perror`、および `strerror` を使用します。<br /><br /> エラー コードと関連情報を格納します。|  
|[_environ、_wenviron](../c-runtime-library/environ-wenviron.md)|非推奨。 代わりに、`getenv_s`、`_wgetenv_s`、`_dupenv_s`、`_wdupenv_s`、`_putenv_s`、および `_wputenv_s` を使用します。<br /><br /> プロセス環境文字列へのポインターの配列へのポインター。起動時に初期化されます。|  
|[_fmode](../c-runtime-library/fmode.md)|非推奨。 代わりに、`_get_fmode` または `_set_fmode` を使用します。<br /><br /> 既定のファイルの変換モードを設定します。|  
|[_iob](../c-runtime-library/iob.md)|コンソール、ファイル、およびデバイスの I/O 制御構造の配列。|  
|[_pctype、_pwctype、_wctype、_mbctype、_mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)|文字分類関数によって使用される情報を格納します。|  
|[_pgmptr、_wpgmptr](../c-runtime-library/pgmptr-wpgmptr.md)|非推奨。 代わりに、`_get_pgmptr` または `_get_wpgmptr` を使用します。<br /><br /> プログラムの起動時に、プログラムの呼び出し方法に応じて、プログラムの完全修飾パスまたは相対パス、完全なプログラム名、またはファイル名拡張子の付かないプログラム名に初期化されます。|  
  
## <a name="see-also"></a>参照  
 [C ランタイム ライブラリ リファレンス](../c-runtime-library/c-run-time-library-reference.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)   
 [__argc、\__argv、\__wargv](../c-runtime-library/argc-argv-wargv.md)   
 [_get_daylight](../c-runtime-library/reference/get-daylight.md)   
 [_get_dstbias](../c-runtime-library/reference/get-dstbias.md)   
 [_get_timezone](../c-runtime-library/reference/get-timezone.md)   
 [_get_tzname](../c-runtime-library/reference/get-tzname.md)   
 [perror](../c-runtime-library/reference/perror-wperror.md)   
 [strerror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)   
 [_get_doserrno](../c-runtime-library/reference/get-doserrno.md)   
 [_set_doserrno](../c-runtime-library/reference/set-doserrno.md)   
 [_get_errno](../c-runtime-library/reference/get-errno.md)   
 [_set_errno](../c-runtime-library/reference/set-errno.md)   
 [_dupenv_s、_wdupenv_s](../c-runtime-library/reference/dupenv-s-wdupenv-s.md)   
 [getenv、_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)   
 [getenv_s、_wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [_putenv、_wputenv](../c-runtime-library/reference/putenv-wputenv.md)   
 [_putenv_s、_wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)   
 [_get_fmode](../c-runtime-library/reference/get-fmode.md)   
 [_set_fmode](../c-runtime-library/reference/set-fmode.md)