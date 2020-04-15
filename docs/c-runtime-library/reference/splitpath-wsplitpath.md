---
title: _splitpath、_wsplitpath
ms.date: 4/2/2020
api_name:
- _wsplitpath
- _splitpath
- _o__splitpath
- _o__wsplitpath
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wsplitpath
- _splitpath
- splitpath
- _wsplitpath
- _tsplitpath
helpviewer_keywords:
- _splitpath function
- pathnames
- wsplitpath function
- splitpath function
- _wsplitpath function
- tsplitpath function
- path names
- _tsplitpath function
ms.assetid: 32bd76b5-1385-4ee8-a64c-abcb541cd2e4
ms.openlocfilehash: 6798f93b2d1bc18a190b3b015bf8c882a3fa8a37
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355608"
---
# <a name="_splitpath-_wsplitpath"></a>_splitpath、_wsplitpath

パス名をコンポーネントに分割します。 これらの関数のセキュリティを強化したバージョンについては、「[_splitpath_s、_wsplitpath_s](splitpath-s-wsplitpath-s.md)」をご覧ください。

## <a name="syntax"></a>構文

```C
void _splitpath(
   const char *path,
   char *drive,
   char *dir,
   char *fname,
   char *ext
);
void _wsplitpath(
   const wchar_t *path,
   wchar_t *drive,
   wchar_t *dir,
   wchar_t *fname,
   wchar_t *ext
);
```

### <a name="parameters"></a>パラメーター

*path*<br/>
完全パス。

*ドライブ*<br/>
ドライブ文字の後にコロン **(:)** を付けます。 ドライブ文字が不要な場合は、このパラメータに**NULL**を渡すことができます。

*Dir*<br/>
末尾のスラッシュを含むディレクトリ パス。 スラッシュ ( **/** )、円記号**\\**( ) またはその両方を使用できます。 ディレクトリ パスが必要ない場合は、このパラメータに**NULL**を渡すことができます。

*Fname*<br/>
基本ファイル名 (拡張子なし)。 ファイル名が必要ない場合は、このパラメータに**NULL**を渡すことができます。

*内線*<br/>
ファイル名拡張子 (先行ピリオド (**. )** を含む)。 ファイル名拡張子が必要ない場合は、このパラメータに**NULL**を渡すことができます。

## <a name="remarks"></a>解説

**_splitpath**関数はパスを 4 つのコンポーネントに分割します。 **_splitpath**は、マルチバイト文字の文字列引数を適切に処理し、現在使用中のマルチバイト コード ページに従ってマルチバイト文字シーケンスを認識します。 **_wsplitpath**は **_splitpath**のワイド文字バージョンです。**_wsplitpath**の引数はワイド文字列です。 それ以外では、これらの関数の動作は同じです。

**セキュリティに関するメモ** これらの関数は、バッファー オーバーランが原因で発生する潜在的な脅威の影響を受けます。 バッファー オーバーランは、システムを攻撃するときによく使用される方法であり、その結果、認められていない権限が昇格されます。 詳しくは、「 [バッファー オーバーランの回避](/windows/win32/SecBP/avoiding-buffer-overruns)」をご覧ください。 これらの関数のより安全なバージョンを使用できます。[_splitpath_s、 _wsplitpath_s](splitpath-s-wsplitpath-s.md)を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath**|**_splitpath**|**_splitpath**|**_wsplitpath**|

完全パスの各コンポーネントは、個別のバッファーに格納されます。マニフェスト**定数は、** **、**_MAX_DIR 、 **_MAX_FNAME**、 および **_MAX_EXT** ( STDLIB で定義されている ) を_MAX_DRIVEします。H) 各ファイル コンポーネントの最大サイズを指定します。 対応するマニフェスト定数よりも大きいファイル コンポーネントでは、ヒープ破損が発生します。

各バッファーは、バッファー オーバーランの発生を回避するために、対応するマニフェスト定数と同じ大きさである必要があります。

マニフェスト定数の値を次の表に示します。

|名前|[値]|
|----------|-----------|
|**_MAX_DRIVE**|3|
|**_MAX_DIR**|256|
|**_MAX_FNAME**|256|
|**_MAX_EXT**|256|

フルパスにコンポーネント (ファイル名など) が含まれていない場合 **、_splitpath**は空の文字列を対応するバッファに割り当てます。

必要ない*パス*以外のパラメーターの **_splitpath**には**NULL**を渡すことができます。

*path*が**NULL**の場合は、「パラメーター[の検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行が続行できる場合 **、errno**は**EINVAL**に設定され、関数は**EINVAL**を返します。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_splitpath**|\<stdlib.h>|
|**_wsplitpath**|\<stdlib.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[_makepath](makepath-wmakepath.md)」の例をご覧ください。

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[_fullpath、_wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath、_wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_splitpath_s、_wsplitpath_s](splitpath-s-wsplitpath-s.md)<br/>
