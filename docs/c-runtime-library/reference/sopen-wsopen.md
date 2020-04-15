---
title: _sopen、_wsopen
ms.date: 4/2/2020
api_name:
- _sopen
- _wsopen
- _o__sopen
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wsopen
- wsopen
- _sopen
- _tsopen
helpviewer_keywords:
- sopen function
- sharing files
- opening files, for sharing
- _sopen function
- wsopen function
- files [C++], opening
- files [C++], sharing
- _wsopen function
ms.assetid: a9d4cccf-06e9-414d-96fa-453fca88cc1f
ms.openlocfilehash: 0ee788823b62d97cdc81e901a812ba25f40359e9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81356398"
---
# <a name="_sopen-_wsopen"></a>_sopen、_wsopen

共有用にファイルを開きます。 これらの関数のより安全なバージョンを使用できます[_wsopen_s _sopen_s。](sopen-s-wsopen-s.md)

## <a name="syntax"></a>構文

```C
int _sopen(
   const char *filename,
   int oflag,
   int shflag [,
   int pmode ]
);
int _wsopen(
   const wchar_t *filename,
   int oflag,
   int shflag [,
   int pmode ]
);
```

### <a name="parameters"></a>パラメーター

*Filename*<br/>
ファイル名。

*オブラグ*<br/>
許可される操作の種類。

*シュフラッグ*<br/>
許可される共有の種類。

*Pmode*<br/>
アクセス許可の設定。

## <a name="return-value"></a>戻り値

これらの各関数は、開かれたファイルのファイル記述子を返します。

*filename*または*OFLAG*が**NULL**ポインターの場合、または*oflag*または*shflag*が有効な値の範囲内にない場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、これらの関数は -1 を返し **、errno**を次のいずれかの値に設定します。

|errno の値|条件|
|-|-|
| **エアッケ** | 指定されたパスがディレクトリであるか、またはファイルが読み取り専用ですが、書き込み用に開く操作が試行されました。 |
| **EEXIST** | **_O_CREAT**フラグと **_O_EXCL**フラグが指定されましたが、*ファイル名*は既に存在します。 |
| **Einval** | 無効*な無効な不正な引数*または*shflag*引数です。 |
| **EMFILE** | ファイル記述子をこれ以上使用できません。 |
| **エノエント** | ファイルまたはパスが見つかりません。 |

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**_sopen**関数は *、ファイル名*で指定されたファイルを開き、 *oflag*と*shflag*で定義された共有読み取りまたは書き込み用にファイルを準備します。 **_wsopen**は **、_sopen**のワイド文字バージョンです。**_wsopen**する*ファイル名*引数はワイド文字列です。 **_wsopen**と **_sopen**は、そうでなければ同じように動作します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsopen**|**_sopen**|**_sopen**|**_wsopen**|

oflag*oflag*の整数式は、fcntl.h>で\<定義されている次のマニフェスト定数の 1 つ以上を組み合わせることによって形成されます。 2 つ以上の定数が*oflag*引数を形成する場合、それらはビットごとの OR 演算子 ( **&#124;** ) と組み合わされます。

|*定値*|動作|
|-|-|
| **_O_APPEND** | 書き込み操作の前に、毎回、ファイル ポインターをファイルの末尾に移動します。 |
| **_O_BINARY** | ファイルをバイナリ (無変換) モードで開きます。 (バイナリ モードの詳細については、「[fopen](fopen-wfopen.md)」を参照してください)。 |
| **_O_CREAT** | ファイルを作成し、書き込み用に開きます。 filename で指定されたファイルが存在する場合は、無効*です*。 **_O_CREAT**を指定する場合は *、pmode*引数が必要です。 |
| **_O_CREAT&#124;_O_SHORT_LIVED** **_O_SHORT_LIVED** | ファイルを一時ファイルとして作成し、可能な場合は、ディスクにフラッシュしません。 **_O_CREAT**を指定する場合は *、pmode*引数が必要です。 |
| **&#124;** **_O_TEMPORARY_O_CREAT** | ファイルを一時ファイルとして作成します。最後のファイル記述子が閉じられると、ファイルは削除されます。 **_O_CREAT**を指定する場合は *、pmode*引数が必要です。 |
| **&#124;_O_CREAT**`_O_EXCL` | filename で指定されたファイルが存在する場合は、エラー値を返*します*。 **_O_CREAT**と共に使用する場合にのみ適用されます。 |
| **_O_NOINHERIT** | 共有ファイル記述子の作成を禁止します。 |
| **_O_RANDOM** | キャッシュがディスクからのランダム アクセスに最適化されるように指定します。ただし、ランダム アクセスに限定されるわけではありません。 |
| **_O_RDONLY** | 読み取り専用でファイルを開きます。 **_O_RDWR**または **_O_WRONLY**では指定できません。 |
| **_O_RDWR** | 読み取りと書き込みの両方用にファイルを開きます。 **_O_RDONLY**または **_O_WRONLY**では指定できません。 |
| **_O_SEQUENTIAL** | キャッシュがディスクからのシーケンシャル アクセスに最適化されるように指定します。ただし、シーケンシャル アクセスに限定されるわけではありません。 |
| **_O_TEXT** | ファイルをテキスト (変換) モードで開きます。 (詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」および「[fopen](fopen-wfopen.md)」を参照してください。) |
| **_O_TRUNC** | ファイルを開き、長さゼロに切り詰めます。ファイルに書き込みアクセス許可が必要です。 **_O_RDONLY**では指定できません。 **_O_TRUNC_O_CREAT**で使用**すると**、既存のファイルを開くか、ファイルを作成します。 **注:****_O_TRUNC**フラグは、指定されたファイルの内容を破棄します。 |
| **_O_WRONLY** | 書き込み専用でファイルを開きます。 **_O_RDONLY**または **_O_RDWR**では指定できません。 |
| **_O_U16TEXT** | Unicode UTF-16 モードでファイルを開きます。 |
| **_O_U8TEXT** | Unicode UTF-8 モードでファイルを開きます。 |
| **_O_WTEXT** | Unicode モードでファイルを開きます。 |

ファイル アクセス モードを指定するには、 **_O_RDONLY**、 **_O_RDWR**、 または **_O_WRONLY**のいずれかを指定する必要があります。 アクセス モードに既定値はありません。

**_O_WTEXT**、 **_O_U8TEXT**、**または _O_U16TEXT**を使用してファイルを Unicode モードで開くと、入力関数は、ファイルから読み取ったデータを**wchar_t**型として格納された UTF-16 データに変換します。 Unicode モードで開かれたファイルに書き込む関数は、型として格納された UTF-16 データを含むバッファー **wchar_t**必要です。 ファイルが UTF-8 としてエンコードされている場合、UTF-16 データは書き込まれるときに UTF-8 に変換され、ファイルの UTF-8 でエンコードされた内容は読み取られるときに UTF-16 に変換されます。 Unicode モードで奇数バイトの読み取りまたは書き込みを試みると、パラメーター検証エラーが発生します。 UTF-8 としてプログラムに格納されたデータを読み取るか書き込む場合は、Unicode モードではなくテキストまたはバイナリ ファイル モードを使用します。 必要なエンコード変換は各自が行う必要があります。

**_sopen**が **_O_APPEND** (追加モード) と **_O_WTEXT**、 **_O_U16TEXT**、または **_O_U8TEXT**で **_O_WRONLY** | 呼び出された場合は、まず読み取りと書き込み用のファイルを開き、BOM を読み取ってから書き込み専用で再度開きます。 読み取りおよび書き込み用にファイルを開くのに失敗した場合、書き込み専用でファイルを開き、Unicode モード設定の既定値を使用します。

引数*shflag*は、次のマニフェスト定数のいずれかから構成される定数式で、share.h \<>で定義されています。

|*シュフラグ*定数|動作|
|-|-|
| **_SH_DENYRW** | ファイルへの読み取りおよび書き込みアクセスを拒否します。 |
| **_SH_DENYWR** | ファイルへの書き込みアクセスを拒否します。 |
| **_SH_DENYRD** | ファイルへの読み取りアクセスを拒否します。 |
| **_SH_DENYNO** | 読み取りおよび書き込みアクセスを許可します。 |

*pmode*引数は **、_O_CREAT**指定されている場合にのみ必要です。 ファイルが存在しない場合 *、pmode*は、新しいファイルが最初に閉じられたときに設定されるファイルのアクセス権設定を指定します。 それ以外の場合 *、pmode*は無視されます。 *pmode*は、sys\stat.h>で\<定義されているマニフェスト定数 **_S_IWRITE**および **_S_IREAD**の一方または両方を含む整数式です。 両方の定数が指定されると、これらはビットごとの OR 演算子を使用して組み合わされます。 *pmode*の意味は以下の通りである。

|*Pmode*|意味|
|-|-|
| **_S_IREAD** | 読み取りのみが許可されます。 |
| **_S_IWRITE** | 書き込みが許可されます。 (実際には、読み取りと書き込みが許可されます)。 |
| **_S_IREAD&#124;_S_IWRITE** **_S_IWRITE** | 読み取りと書き込みが許可されます。 |

書き込みアクセス許可が与えられない場合、ファイルは読み取り専用になります。 Windows オペレーティング システムでは、すべてのファイルは読み取り可能です。書き込み専用のアクセス許可を与えることはできません。 したがって、モード **_S_IWRITE**と **_S_IREAD_S_IWRITE** | **_S_IWRITE**は同等です。

**_sopen**アクセス権が設定される前に、現在のファイルアクセス権マスクを*pmode*に適用します。 (「[_umask](umask.md)」を参照。)

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_sopen**|\<io.h>|\<fcntl.h>、\<sys\types.h>、\<sys\stat.h>、\<share.h>|
|**_wsopen**|\<io.h> または \<wchar.h>|\<fcntl.h>、\<sys\types.h>、\<sys\stat.h>、\<share.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

「[_locking](locking.md)」の例をご覧ください。

## <a name="see-also"></a>関連項目

[下位入出力](../../c-runtime-library/low-level-i-o.md)<br/>
[_close](close.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[fopen、_wfopen](fopen-wfopen.md)<br/>
[_fsopen、_wfsopen](fsopen-wfsopen.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
