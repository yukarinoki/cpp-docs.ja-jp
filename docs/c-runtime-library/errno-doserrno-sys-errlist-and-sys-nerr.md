---
title: errno、_doserrno、_sys_errlist、_sys_nerr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _errno
apilocation:
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- _sys_errlist
- errno
- _sys_nerr
- _doserrno
dev_langs:
- C++
helpviewer_keywords:
- error codes, printing
- sys_errlist global variable
- doserrno global variable
- errno global variable
- _doserrno global variable
- _sys_errlist global variable
- _sys_nerr global variable
- sys_nerr global variable
ms.assetid: adbec641-6d91-4e19-8398-9a34046bd369
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b17abb975ea9f3212d4bd6171bcd2bffb78e483c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="errno-doserrno-syserrlist-and-sysnerr"></a>errno、_doserrno、_sys_errlist、および _sys_nerr
プログラムの実行中に設定されるエラー コードと、エラー コードに相当する表示用の文字列を保持するグローバル マクロ。  
  
## <a name="syntax"></a>構文  
  
```  
#define errno   (*_errno())  
#define _doserrno   (*__doserrno())  
#define _sys_errlist (__sys_errlist())  
#define _sys_nerr (*__sys_nerr())  
```  
  
## <a name="remarks"></a>コメント  
 `errno` と `_doserrno` は両方とも、プログラムの起動中にランタイムによって 0 に設定されます。 システム レベルの呼び出しでエラーが発生すると、`errno` が設定されます。 `errno` には最後の呼び出しで設定された値が保持されるため、この値は、その後の呼び出しによって変更される可能性があります。 エラーの発生時に `errno` を設定するランタイム ライブラリの呼び出しでは、正常に完了しても、`errno` はクリアされません。 `errno` は、これを設定する呼び出しの直前に `_set_errno(0)` を呼び出して必ずクリアし、呼び出しの直後に確認します。  
  
 エラーの発生時、`errno` は、必ずしもシステム呼び出しで返されるエラー コードと同じ値に設定されるとは限りません。 I/O 操作では、`_doserrno` に `errno` コードと同等のオペレーティング システムのエラー コードが格納されます。 I/O 以外の操作については、ほとんどの場合、`_doserrno` の値は設定されません。  
  
 各 `errno` 値は、`_sys_errlist` のエラー メッセージに関連付けられており、これは [perror](../c-runtime-library/reference/perror-wperror.md) 関数のいずれかを使用して出力するか、[strerror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md) または [strerror_s](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md) 関数のいずれかを使用して文字列に格納できます。 `perror` および `strerror` 関数は、`_sys_errlist` 配列と `_sys_nerr` (`_sys_errlist` の要素の数) を使用して、エラー情報を処理します。 `_sys_errlist` および `_sys_nerr` への直接アクセスは、コードのセキュリティ上の理由から推奨されていません。 次に示すように、グローバル マクロではなく、より安全かつ機能的なバージョンを使用することをお勧めします。  
  
|グローバル マクロ|機能的に同等なバージョン|  
|------------------|----------------------------|  
|`_doserrno`|[_get_doserrno](../c-runtime-library/reference/get-doserrno.md)、[_set_doserrno](../c-runtime-library/reference/set-doserrno.md)|  
|`errno`|[_get_errno](../c-runtime-library/reference/get-errno.md)、[_set_errno](../c-runtime-library/reference/set-errno.md)|  
|`_sys_errlist`, `_sys_nerr`|[strerror_s、_strerror_s、_wcserror_s、\__wcserror_s](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)|  
  
 ライブラリの数値演算ルーチンでは、[_matherr](../c-runtime-library/reference/matherr.md) を呼び出して `errno` を設定します。 別の方法で数値演算エラーを処理するには、`_matherr` リファレンスの説明に従って独自のルーチンを記述し、`_matherr` という名前を付けます。  
  
 次の表のすべての `errno` 値が \<errno.h> の定義済み定数で、UNIX と互換性があります。 `ERANGE`、`EILSEQ`、および `EDOM` のみが、ISO C99 標準で指定されます。  
  
|定数|システム エラー メッセージ|[値]|  
|--------------|--------------------------|-----------|  
|`EPERM`|操作は許可されていません|1|  
|`ENOENT`|該当するファイルまたはディレクトリがありません|2|  
|`ESRCH`|該当するプロセスがありません|3|  
|`EINTR`|関数に割り込みがありました|4|  
|`EIO`|I/O エラーです|5|  
|`ENXIO`|該当するデバイスまたはアドレスがありません|6|  
|`E2BIG`|引数が長すぎます|7|  
|`ENOEXEC`|実行形式エラーです|8|  
|`EBADF`|ファイル番号が正しくありません|9|  
|`ECHILD`|子プロセスが存在しません|10|  
|`EAGAIN`|これ以上プロセスを生成できないか、メモリが不足しているか、最大の入れ子レベルに達しました|11|  
|`ENOMEM`|メモリが不足しています|12|  
|`EACCES`|アクセス許可は拒否されました|13|  
|`EFAULT`|アドレスが正しくありません|14|  
|`EBUSY`|デバイスまたはリソースがビジー状態です|16|  
|`EEXIST`|ファイルが存在します|17|  
|`EXDEV`|クロス デバイス リンクがあります|18|  
|`ENODEV`|該当するデバイスがありません|19|  
|`ENOTDIR`|ディレクトリではありません|20|  
|`EISDIR`|ディレクトリです|21|  
|`EINVAL`|引数が無効です|22|  
|`ENFILE`|システムで開いているファイルが多すぎます|23|  
|`EMFILE`|開いているファイルが多すぎます|24|  
|`ENOTTY`|不適切な I/O 制御操作です|25|  
|`EFBIG`|ファイルが大きすぎます|27|  
|`ENOSPC`|デバイスに空き領域がありません|28|  
|`ESPIPE`|シークが無効です|29|  
|`EROFS`|読み取り専用ファイル システムが使用されています|30|  
|`EMLINK`|リンクが多すぎます|31|  
|`EPIPE`|パイプが破壊されています|32|  
|`EDOM`|算術演算引数が使用されました|33|  
|`ERANGE`|結果が大きすぎます|34|  
|`EDEADLK`|リソース デッドロックが発生します|36|  
|`EDEADLOCK`|古いバージョンの Microsoft C との互換性のために EDEADLK と同じです|36|  
|`ENAMETOOLONG`|ファイル名が長すぎます|38|  
|`ENOLCK`|ロックがありません|39|  
|`ENOSYS`|関数はサポートされていません|40|  
|`ENOTEMPTY`|ディレクトリが空ではありません|41|  
|`EILSEQ`|無効なバイト シーケンスです|42|  
|`STRUNCATE`|残りの文字列は切り詰められました|80|  
  
## <a name="requirements"></a>必要条件  
  
|グローバル マクロ|必須ヘッダー|オプション ヘッダー|  
|------------------|---------------------|---------------------|  
|`errno`|\<errno.h> または \<stdlib.h>、\<cerrno> または \<cstdlib> (C++)||  
|`_doserrno`、`_sys_errlist`、`_sys_nerr`|\<stdlib.h>、\<cstdlib> (C++)|\<errno.h>、\<cerrno> (C++)|  
  
 `_doserrno`、`_sys_errlist`、および `_sys_nerr` マクロは Microsoft 拡張機能です。 互換性について詳しくは、「[互換性](../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="see-also"></a>参照  
 [グローバル変数](../c-runtime-library/global-variables.md)   
 [errno 定数](../c-runtime-library/errno-constants.md)   
 [perror、_wperror](../c-runtime-library/reference/perror-wperror.md)   
 [strerror、_strerror、_wcserror、\__wcserror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)   
 [strerror_s、_strerror_s、_wcserror_s、\__wcserror_s](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)   
 [_get_doserrno](../c-runtime-library/reference/get-doserrno.md)   
 [_set_doserrno](../c-runtime-library/reference/set-doserrno.md)   
 [_get_errno](../c-runtime-library/reference/get-errno.md)   
 [_set_errno](../c-runtime-library/reference/set-errno.md)