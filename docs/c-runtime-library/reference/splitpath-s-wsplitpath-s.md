---
title: _splitpath_s、_wsplitpath_s
ms.date: 4/2/2020
api_name:
- _wsplitpath_s
- _splitpath_s
- _o__splitpath_s
- _o__wsplitpath_s
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wsplitpath_s
- splitpath_s
- _splitpath_s
- wsplitpath_s
helpviewer_keywords:
- splitpath_s function
- pathnames
- _splitpath_s function
- _wsplitpath_s function
- path names
- wsplitpath_s function
ms.assetid: 30fff3e2-cd00-4eb6-b5a2-65db79cb688b
ms.openlocfilehash: 364544a9423668494747405e801d59b73de4e6c6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355618"
---
# <a name="_splitpath_s-_wsplitpath_s"></a>_splitpath_s、_wsplitpath_s

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
完全パス。

*ドライブ*<br/>
ドライブ文字の後にコロン **(:)** を付けます。 ドライブ文字が不要な場合は、このパラメータに**NULL**を渡すことができます。

*要素数*<br/>
1 バイト文字またはワイド文字で表される*ドライブ*・バッファーのサイズ。 *ドライブ*が**NULL**の場合、この値は 0 である必要があります。

*Dir*<br/>
末尾のスラッシュを含むディレクトリ パス。 スラッシュ ( **/** )、円記号**\\**( ) またはその両方を使用できます。 ディレクトリ パスが必要ない場合は、このパラメータに**NULL**を渡すことができます。

*要素数*<br/>
1 バイト文字またはワイド文字の*dir*バッファーのサイズ。 *dir*が**NULL**の場合、この値は 0 でなければなりません。

*Fname*<br/>
拡張子なしの基本ファイル名。 ファイル名が必要ない場合は、このパラメータに**NULL**を渡すことができます。

*要素の名前*<br/>
1 バイト文字またはワイド文字での*fname*バッファーのサイズ。 *fname*が**NULL**の場合、この値は 0 でなければなりません。

*内線*<br/>
ファイル名拡張子 (先行ピリオド (**. )** を含む)。ファイル名拡張子が必要ない場合は、このパラメータに**NULL**を渡すことができます。

*要素数*<br/>
1 バイト文字またはワイド文字の*内線*バッファのサイズ。 *ext*が**NULL**の場合、この値は 0 である必要があります。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

### <a name="error-conditions"></a>エラー条件

|条件|戻り値|
|---------------|------------------|
|*パス*が**NULL です**|**Einval**|
|*ドライブ*が**NULL、***ドライブ番号の要素*は 0 以外です。|**Einval**|
|*ドライブ*が**NULL**以外の場合、*ドライブ番号の要素*はゼロです。|**Einval**|
|*ディレクトリ*が**NULL、***ディレクトリ番号の要素*は 0 以外です。|**Einval**|
|*dir*は**NULL**以外の値で、*要素数*はゼロです。|**Einval**|
|*fname*が**NULL**、*名前数値Of要素*が 0 以外の場合|**Einval**|
|*fname*は**NULL**以外の値で、*名前NumberOf要素*はゼロです|**Einval**|
|*内線*が**NULL、***内線番号の要素*は 0 以外です。|**Einval**|
|*内線*は**NULL**以外の値で、*要素数*はゼロです。|**Einval**|

上記のいずれかの条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、これらの関数は**errno**を**EINVAL**に設定し **、EINVAL**を返します。

バッファのいずれかが短すぎて結果を保持できなければ、これらの関数はすべてのバッファを空の文字列にクリアし **、errno**を**ERANGE**に設定して**ERANGE**を返します。

## <a name="remarks"></a>解説

**_splitpath_s**関数はパスを 4 つのコンポーネントに分割します。 **_splitpath_s**は、マルチバイト文字の文字列引数を適切に処理し、現在使用中のマルチバイトコードページに従ってマルチバイト文字シーケンスを認識します。 **_wsplitpath_s**はワイド文字の **_splitpath_s**です。**_wsplitpath_s**の引数はワイド文字列です。 それ以外では、これらの関数の動作は同じです

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath_s**|**_splitpath_s**|**_splitpath_s**|**_wsplitpath_s**|

完全パスの各コンポーネントは、個別のバッファーに格納されます。マニフェスト**定数は、** **、**_MAX_DIR 、 **_MAX_FNAME**、 および **_MAX_EXT** ( STDLIB で定義されている ) を_MAX_DRIVEします。H) 各ファイル コンポーネントの最大許容サイズを指定します。 対応するマニフェスト定数よりも大きいファイル コンポーネントでは、ヒープ破損が発生します。

マニフェスト定数の値を次の表に示します。

|名前|[値]|
|----------|-----------|
|_MAX_DRIVE|3|
|_MAX_DIR|256|
|_MAX_FNAME|256|
|_MAX_EXT|256|

フルパスにコンポーネント (ファイル名など) が含まれていない場合 **、_splitpath_s**は空の文字列を対応するバッファに割り当てます。

C++ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

これらの関数のデバッグ ライブラリ バージョンは、まずバッファーに 0xFE を設定します。 この動作を無効にするには、[_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md) を使用します。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_splitpath_s**|\<stdlib.h>|
|**_wsplitpath_s**|\<stdlib.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[_makepath_s、_wmakepath_s](makepath-s-wmakepath-s.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[_splitpath、_wsplitpath](splitpath-wsplitpath.md)<br/>
[_fullpath、_wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath、_wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
