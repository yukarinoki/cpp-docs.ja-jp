---
title: _splitpath、_wsplitpath | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wsplitpath
- _splitpath
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
- wsplitpath
- _splitpath
- splitpath
- _wsplitpath
- _tsplitpath
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 46d29b55e215ce426bbfd465b3d54e1d267a1bb1
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44103919"
---
# <a name="splitpath-wsplitpath"></a>_splitpath、_wsplitpath

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
完全なパス。

*ドライブ*<br/>
ドライブ文字、コロン (**:**)。 渡すことができます**NULL**ドライブ文字を必要としない場合は、このパラメーターにします。

*dir*<br/>
末尾のスラッシュを含むディレクトリ パス。 スラッシュ ( **/** )、円記号 ( **\\** )、または両方を使用できます。 渡すことができます**NULL**ディレクトリ パスを必要としない場合は、このパラメーターにします。

*fname*<br/>
基本ファイル名 (拡張子なし)。 渡すことができます**NULL**ファイル名を必要としない場合は、このパラメーターにします。

*ext*<br/>
先頭のピリオドを含むファイル名の拡張子 (**.**)。 渡すことができます**NULL**ファイル名拡張子が必要ない場合は、このパラメーターにします。

## <a name="remarks"></a>Remarks

**_Splitpath**関数は、4 つのコンポーネントにパスを解除します。 **_splitpath**自動的に現在使用中のマルチバイト コード ページに従ってマルチバイト文字シーケンスを認識し、必要に応じてマルチバイト文字の文字列引数を処理します。 **_wsplitpath**のワイド文字バージョンは、 **_splitpath**; 引数 **_wsplitpath**はワイド文字列です。 それ以外では、これらの関数の動作は同じです。

**セキュリティに関するメモ**これらの関数は、バッファー オーバーランの問題によって潜在的な脅威を引き起こすことがあります。 バッファー オーバーランは、システムを攻撃するときによく使用される方法であり、その結果、認められていない権限が昇格されます。 詳しくは、「 [バッファー オーバーランの回避](/windows/desktop/SecBP/avoiding-buffer-overruns)」をご覧ください。 これらの関数のセキュリティを強化したバージョンについては、「[_splitpath_s、_wsplitpath_s](splitpath-s-wsplitpath-s.md)」をご覧ください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath**|**_splitpath**|**_splitpath**|**_wsplitpath**|

完全なパスの各コンポーネントが別々 のバッファーに格納されています。マニフェスト定数 **_MAX_DRIVE**、 **_MAX_DIR**、 **_MAX_FNAME**、および **_MAX_EXT** (STDLIB で定義されています。H) ファイルの各コンポーネントの最大サイズを指定します。 対応するマニフェスト定数よりも大きいファイル コンポーネントでは、ヒープ破損が発生します。

各バッファーは、バッファー オーバーランの発生を回避するために、対応するマニフェスト定数と同じ大きさである必要があります。

マニフェスト定数の値を次の表に示します。

|名前|[値]|
|----------|-----------|
|**_MAX_DRIVE**|3|
|**_MAX_DIR**|256|
|**_MAX_FNAME**|256|
|**_MAX_EXT**|256|

完全なパスにコンポーネント (たとえば、filename) が含まれていない場合 **_splitpath**対応するバッファーに文字列を空に割り当てます。

渡すことができます**NULL**に **_splitpath**以外の任意のパラメーターの*パス*する必要はありません。

場合*パス*は**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL** 、関数を返します**EINVAL**します。

## <a name="requirements"></a>要件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_splitpath**|\<stdlib.h>|
|**_wsplitpath**|\<stdlib.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[_makepath](makepath-wmakepath.md)」の例をご覧ください。

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[_fullpath、_wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath、_wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_splitpath_s、_wsplitpath_s](splitpath-s-wsplitpath-s.md)<br/>
