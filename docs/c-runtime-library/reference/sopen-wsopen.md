---
title: _sopen、_wsopen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _sopen
- _wsopen
apilocation:
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
apitype: DLLExport
f1_keywords:
- _wsopen
- wsopen
- _sopen
- _tsopen
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e8d7f7624dc8c521186aa697ad8825c77e0108f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418102"
---
# <a name="sopen-wsopen"></a>_sopen、_wsopen

共有用にファイルを開きます。 これらの関数のより安全なバージョンが利用可能: を参照してください[_sopen_s、_wsopen_s](sopen-s-wsopen-s.md)です。

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

*ファイル名*<br/>
ファイル名。

*oflag*<br/>
許可される操作の種類。

*shflag*<br/>
許可される共有の種類。

*pmode*<br/>
アクセス許可の設定。

## <a name="return-value"></a>戻り値

これらの各関数は、開かれたファイルのファイル記述子を返します。

場合*filename*または*oflag*は、 **NULL**ポインター、または*oflag*または*shflag*が有効な内にありません範囲の値、無効なパラメーター ハンドラーが呼び出される」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、これらの関数は-1 を返します設定と**errno**値は次のいずれかにします。

|errno の値|条件|
|-|-|
**EACCES**|指定されたパスがディレクトリであるか、またはファイルが読み取り専用ですが、書き込み用に開く操作が試行されました。
**EEXIST**|**_O_CREAT**と **_O_EXCL**フラグが指定されましたが、 *filename*既に存在します。
**EINVAL**|無効な*oflag*または*shflag*引数。
**EMFILE**|ファイル記述子をこれ以上使用できません。
**ENOENT**|ファイルまたはパスが見つかりません。

リターン コードの詳細については、「 [_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>コメント

**_Sopen**関数は指定されたファイルを開きます*filename*による定義に従って、共有読み取りまたは書き込みのファイルを準備および*oflag*と*shflag*. **_wsopen**のワイド文字バージョンは、 **_sopen**以外の場合は、 *filename*に渡す引数 **_wsopen**ワイド文字列です。 **_wsopen**と **_sopen**それ以外の場合の動作は同じです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsopen**|**_sopen**|**_sopen**|**_wsopen**|

整数型の式*oflag*で定義されている次のマニフェスト定数の 1 つ以上を組み合わせることで形成される\<fcntl.h >。 2 つ以上の定数で、引数を構成するときに*oflag*、これらはビットごとの OR 演算子で組み合わされます ( **&#124;** )。

|*oflag*定数|動作|
|-|-|
**_O_APPEND**|書き込み操作の前に、毎回、ファイル ポインターをファイルの末尾に移動します。
**_O_BINARY**|ファイルをバイナリ (無変換) モードで開きます。 (バイナリ モードの詳細については、「[fopen](fopen-wfopen.md)」を参照してください)。
**_O_CREAT**|ファイルを作成し、書き込み用に開きます。 によってファイルが指定された場合は、影響を与えません*filename*が存在します。 *Pmode*引数が必要なときに **_O_CREAT**を指定します。
**_O_CREAT** &AMP;#124; **_O_SHORT_LIVED**|ファイルを一時ファイルとして作成し、可能な場合は、ディスクにフラッシュしません。 *Pmode*引数が必要なときに **_O_CREAT**を指定します。
**_O_CREAT** &AMP;#124; **_O_TEMPORARY**|ファイルを一時ファイルとして作成します。最後のファイル記述子が閉じられると、ファイルは削除されます。 *Pmode*引数が必要なときに **_O_CREAT**を指定します。
**_O_CREAT**&AMP;#124; ` _O_EXCL`|場合によって指定されたファイルは、エラー値を返します*filename*が存在します。 使用する場合にのみ適用されます **_O_CREAT**です。
**_O_NOINHERIT**|共有ファイル記述子の作成を禁止します。
**_O_RANDOM**|キャッシュがディスクからのランダム アクセスに最適化されるように指定します。ただし、ランダム アクセスに限定されるわけではありません。
**_O_RDONLY**|読み取り専用でファイルを開きます。 と共に指定できません **_O_RDWR**または **_O_WRONLY**です。
**_O_RDWR**|読み取りと書き込みの両方用にファイルを開きます。 と共に指定できません **_O_RDONLY**または **_O_WRONLY**です。
**_O_SEQUENTIAL**|キャッシュがディスクからのシーケンシャル アクセスに最適化されるように指定します。ただし、シーケンシャル アクセスに限定されるわけではありません。
**_O_TEXT**|ファイルをテキスト (変換) モードで開きます。 (詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」および「[fopen](fopen-wfopen.md)」を参照してください。)
**_O_TRUNC**|ファイルを開き、長さゼロに切り詰めます。ファイルに書き込みアクセス許可が必要です。 と共に指定できません **_O_RDONLY**です。 **_O_TRUNC**併用 **_O_CREAT**既存のファイルを開くか、ファイルを作成します。 **注:** 、 **_O_TRUNC**フラグが指定されたファイルの内容を破棄します。
**_O_WRONLY**|書き込み専用でファイルを開きます。 と共に指定できません **_O_RDONLY**または **_O_RDWR**です。
**_O_U16TEXT**|Unicode UTF-16 モードでファイルを開きます。
**_O_U8TEXT**|Unicode UTF-8 モードでファイルを開きます。
**_O_WTEXT**|Unicode モードでファイルを開きます。

ファイル アクセス モードを指定する、いずれかを指定する必要があります **_O_RDONLY**、 **_O_RDWR**、または **_O_WRONLY**です。 アクセス モードに既定値はありません。

使用して Unicode モードでファイルが開かれると **_O_WTEXT**、 **_O_U8TEXT**、または **_O_U16TEXT**、input 関数は、utf-16 データに、ファイルから読み取られるデータを変換型として格納された**wchar_t**です。 Unicode モードで開かれたファイルに書き込む関数は型として格納された utf-16 データを含んでいるバッファーを想定して**wchar_t**です。 ファイルが UTF-8 としてエンコードされている場合、UTF-16 データは書き込まれるときに UTF-8 に変換され、ファイルの UTF-8 でエンコードされた内容は読み取られるときに UTF-16 に変換されます。 Unicode モードで奇数バイトの読み取りまたは書き込みを試みると、パラメーター検証エラーが発生します。 UTF-8 としてプログラムに格納されたデータを読み取るか書き込む場合は、Unicode モードではなくテキストまたはバイナリ ファイル モードを使用します。 必要なエンコード変換は各自が行う必要があります。

場合 **_sopen**で呼び出された **_O_WRONLY** | **_O_APPEND** (追加モード) および **_O_WTEXT**、 **_O_U16TEXT**、または **_O_U8TEXT**BOM を読み取ってまず読み取りと書き込みのファイルを開こうとして、書き込み専用のウィンドウを開きます。 読み取りおよび書き込み用にファイルを開くのに失敗した場合、書き込み専用でファイルを開き、Unicode モード設定の既定値を使用します。

引数*shflag*で定義されている次のマニフェスト定数のいずれかで構成される定数式は、 \<share.h >。

|*shflag*定数|動作|
|-|-|
**_SH_DENYRW**|ファイルへの読み取りおよび書き込みアクセスを拒否します。
**_SH_DENYWR**|ファイルへの書き込みアクセスを拒否します。
**_SH_DENYRD**|ファイルへの読み取りアクセスを拒否します。
**_SH_DENYNO**|読み取りおよび書き込みアクセスを許可します。

*Pmode*引数が必要な場合にのみ **_O_CREAT**を指定します。 ファイルが存在しない場合*pmode*新しいファイルには、最初の時間が閉じられたときに設定されているファイルのアクセス許可の設定を指定します。 それ以外の場合、 *pmode*は無視されます。 *pmode*マニフェスト定数の一方または両方を含む整数式です **_S_IWRITE**と **_S_IREAD**で定義されている\<sys \stat.h >。 両方の定数が指定されると、これらはビットごとの OR 演算子を使用して組み合わされます。 意味*pmode*のとおりです。

|*pmode*|説明|
|-|-|
**_S_IREAD**|読み取りのみが許可されます。
**_S_IWRITE**|書き込みが許可されます。 (実際には、読み取りと書き込みが許可されます)。
**_S_IREAD** &AMP;#124; **_S_IWRITE**|読み取りと書き込みが許可されます。

書き込みアクセス許可が与えられない場合、ファイルは読み取り専用になります。 Windows オペレーティング システムでは、すべてのファイルは読み取り可能です。書き込み専用のアクセス許可を与えることはできません。 そのため、モード **_S_IWRITE**と **_S_IREAD** | **_S_IWRITE**は同等です。

**_sopen**を現在のファイルのアクセス許可マスクを適用*pmode*アクセス許可を設定する前にします。 (「[_umask](umask.md)」を参照。)

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_sopen**|\<io.h>|\<fcntl.h>、\<sys\types.h>、\<sys\stat.h>、\<share.h>|
|**_wsopen**|\<io.h> または \<wchar.h>|\<fcntl.h>、\<sys\types.h>、\<sys\stat.h>、\<share.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[_locking](locking.md)」の例をご覧ください。

## <a name="see-also"></a>関連項目

[下位入出力](../../c-runtime-library/low-level-i-o.md)<br/>
[_close](close.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[fopen、_wfopen](fopen-wfopen.md)<br/>
[_fsopen、_wfsopen](fsopen-wfsopen.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
