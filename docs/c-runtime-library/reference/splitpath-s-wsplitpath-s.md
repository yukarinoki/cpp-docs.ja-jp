---
title: _splitpath_s、_wsplitpath_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wsplitpath_s
- _splitpath_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wsplitpath_s
- splitpath_s
- _splitpath_s
- wsplitpath_s
dev_langs:
- C++
helpviewer_keywords:
- splitpath_s function
- pathnames
- _splitpath_s function
- _wsplitpath_s function
- path names
- wsplitpath_s function
ms.assetid: 30fff3e2-cd00-4eb6-b5a2-65db79cb688b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5fd1407aa6c2b7630e0720eeec179ca27e7d31a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417433"
---
# <a name="splitpaths-wsplitpaths"></a>_splitpath_s、_wsplitpath_s

パス名をコンポーネントに分割します。 これらは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_splitpath、_wsplitpath](splitpath-wsplitpath.md) です。

## <a name="syntax"></a>構文

```C
errno_t _splitpath_s(
   const char * path,
   char * drive,
   size_t driveNumberOfElements,
   char * dir,
   size_t dirNumberOfElements,
   char * fname,
   size_t nameNumberOfElements,
   char * ext,
   size_t extNumberOfElements
);
errno_t _wsplitpath_s(
   const wchar_t * path,
   wchar_t * drive,
   size_t driveNumberOfElements,
   wchar_t *dir,
   size_t dirNumberOfElements,
   wchar_t * fname,
   size_t nameNumberOfElements,
   wchar_t * ext,
   size_t extNumberOfElements
);
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>
errno_t _splitpath_s(
   const char *path,
   char (&drive)[drivesize],
   char (&dir)[dirsize],
   char (&fname)[fnamesize],
   char (&ext)[extsize]
); // C++ only
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>
errno_t _wsplitpath_s(
   const wchar_t *path,
   wchar_t (&drive)[drivesize],
   wchar_t (&dir)[dirsize],
   wchar_t (&fname)[fnamesize],
   wchar_t (&ext)[extsize]
); // C++ only
```

### <a name="parameters"></a>パラメーター

*path*<br/>
完全なパス。

*ドライブ*<br/>
ドライブ文字、コロン (**:**)。 渡すことができます**NULL**ドライブ文字を必要としない場合は、このパラメーターにします。

*driveNumberOfElements*<br/>
サイズ、*ドライブ*1 バイト文字またはワイド文字バッファー。 場合*ドライブ*は**NULL**、この値は 0 である必要があります。

*dir*<br/>
末尾のスラッシュを含むディレクトリ パス。 スラッシュ ( **/** )、円記号 ( **\\** )、または両方を使用することがあります。 渡すことができます**NULL**ディレクトリ パスを必要としない場合は、このパラメーターにします。

*dirNumberOfElements*<br/>
サイズ、 *dir* 1 バイト文字またはワイド文字バッファー。 場合*dir*は**NULL**、この値は 0 である必要があります。

*fname*<br/>
拡張子なしの基本ファイル名。 渡すことができます**NULL**ファイル名を必要としない場合は、このパラメーターにします。

*nameNumberOfElements*<br/>
サイズ、 *fname* 1 バイト文字またはワイド文字バッファー。 場合*fname*は**NULL**、この値は 0 である必要があります。

*ext*<br/>
ファイル名の拡張子期間 (**.**)。渡すことができます**NULL**ファイル名拡張子を必要としない場合は、このパラメーターにします。

*extNumberOfElements*<br/>
サイズ*ext* 1 バイト文字またはワイド文字バッファー。 場合*ext*は**NULL**、この値は 0 である必要があります。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

### <a name="error-conditions"></a>エラー条件

|条件|戻り値|
|---------------|------------------|
|*パス*は**NULL**|**EINVAL**|
|*ドライブ*は**NULL**、 *driveNumberOfElements* 0 以外には|**EINVAL**|
|*ドライブ*以外**NULL**、 *driveNumberOfElements*ゼロ|**EINVAL**|
|*dir*は**NULL**、 *dirNumberOfElements* 0 以外には|**EINVAL**|
|*dir*以外**NULL**、 *dirNumberOfElements*ゼロ|**EINVAL**|
|*fname*は**NULL**、 *nameNumberOfElements* 0 以外には|**EINVAL**|
|*fname*以外**NULL**、 *nameNumberOfElements*ゼロ|**EINVAL**|
|*ext*は**NULL**、 *extNumberOfElements* 0 以外には|**EINVAL**|
|*ext*以外**NULL**、 *extNumberOfElements*ゼロ|**EINVAL**|

上記のいずれかの条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合に、これらの関数が設定**errno**に**EINVAL**返す**EINVAL**です。

これらの関数が空の文字列を設定するすべてのバッファーをクリア、バッファーのいずれかが、結果を保持するには短すぎる場合は、 **errno**に**ERANGE**、返す**ERANGE**です。

## <a name="remarks"></a>コメント

**_Splitpath_s**関数は、4 つのコンポーネントにパスを解除します。 **_splitpath_s**自動的に現在使用中のマルチバイト コード ページに基づいてマルチバイト文字シーケンスを認識し、必要に応じてマルチバイト文字の文字列引数を処理します。 **_wsplitpath_s**のワイド文字バージョンは、 **_splitpath_s**; 引数 **_wsplitpath_s**ワイド文字列です。 それ以外では、これらの関数の動作は同じです

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath_s**|**_splitpath_s**|**_splitpath_s**|**_wsplitpath_s**|

完全なパスの各コンポーネントが別々 のバッファーに格納されています。マニフェスト定数 **_MAX_DRIVE**、 **_MAX_DIR**、 **_MAX_FNAME**、および **_MAX_EXT** (STDLIB で定義されます。H) ファイルの各コンポーネントの最大許容サイズを指定します。 対応するマニフェスト定数よりも大きいファイル コンポーネントでは、ヒープ破損が発生します。

マニフェスト定数の値を次の表に示します。

|名前|[値]|
|----------|-----------|
|_MAX_DRIVE|3|
|_MAX_DIR|256|
|_MAX_FNAME|256|
|_MAX_EXT|256|

完全なパスにコンポーネント (たとえば、filename) が含まれていない場合 **_splitpath_s**対応するバッファーに空の文字列を割り当てます。

C++ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

これらの関数のデバッグ バージョンは、最初にバッファーを 0xFD で埋めます。 この動作を無効にするには、[_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).を使用します。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_splitpath_s**|\<stdlib.h>|
|**_wsplitpath_s**|\<stdlib.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[_makepath_s、_wmakepath_s](makepath-s-wmakepath-s.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[_splitpath、_wsplitpath](splitpath-wsplitpath.md)<br/>
[_fullpath、_wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath、_wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
