---
title: _CrtIsMemoryBlock
ms.date: 11/04/2016
apiname:
- _CrtIsMemoryBlock
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
apitype: DLLExport
f1_keywords:
- CrtlsMemoryBlock
- _CrtIsMemoryBlock
helpviewer_keywords:
- _CrtIsMemoryBlock function
- CrtIsMemoryBlock function
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
ms.openlocfilehash: c4a85ebeb45552c6f5355853de2a45766d6bc984
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555746"
---
# <a name="crtismemoryblock"></a>_CrtIsMemoryBlock

指定されたメモリ ブロックがローカル ヒープ内にあり、有効なデバッグ ヒープ ブロック型識別子が設定されていることを検査します (デバッグ バージョンだけ)。

## <a name="syntax"></a>構文

```C
int _CrtIsMemoryBlock(
   const void *userData,
   unsigned int size,
   long *requestNumber,
   char **filename,
   int *linenumber
);
```

### <a name="parameters"></a>パラメーター

*userData*<br/>
検査するメモリ ブロックの先頭へのポインター。

*size*<br/>
指定されたブロックのサイズ (バイト)。

*requestNumber*<br/>
ブロックの割り当て番号へのポインターまたは**NULL**します。

*ファイル名*<br/>
ブロックを要求したソース ファイルの名前へのポインターまたは**NULL**します。

*行番号*<br/>
ソース ファイル内の行番号へのポインターまたは**NULL**します。

## <a name="return-value"></a>戻り値

**_CrtIsMemoryBlock**返します**TRUE**場合、指定されたメモリ ブロックがローカル ヒープ内にあるが有効なデバッグ ヒープ ブロック型識別子です。 それ以外の場合、関数を返します**FALSE**します。

## <a name="remarks"></a>Remarks

**_CrtIsMemoryBlock**関数は、指定されたメモリ ブロックがアプリケーションのローカル ヒープ内にあることと、有効なブロック型識別子を使用していることを確認します。 また、この関数を使用すると、オブジェクト割り当て順序番号と、メモリ ブロックの割り当て要求を行ったソース ファイル名および行番号を取得できます。 渡す以外**NULL**の値を*requestNumber*、 *filename*、または*linenumber*パラメーター原因 **_CrtIsMemoryBlock**ローカル ヒープ内のブロックが見つかった場合は、メモリ ブロックのデバッグのヘッダーの値にこれらのパラメーターを設定します。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない、呼び出し **_CrtIsMemoryBlock**プリプロセス時に削除されます。

場合 **_CrtIsMemoryBlock**失敗すると、それを返します**FALSE**され、出力パラメーターが既定値に初期化されます*requestNumber*と**lineNumber。** を 0 に設定されてと*filename*に設定されている**NULL**します。

この関数は **TRUE** または **FALSE** を返すため、[_ASSERT](assert-asserte-assert-expr-macros.md) 系マクロに渡すことによって、デバッグ用の単純なエラー処理機構を作成できます。 指定されたアドレスがローカル ヒープ内にない場合に、アサーションの失敗を発生させるには、次のように記述します。

```C
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,
          &filename, &linenumber ) );
```

詳細について **_CrtIsMemoryBlock**他のデバッグ関数およびマクロとで使用できるを参照してください[レポート用マクロ](/visualstudio/debugger/macros-for-reporting)します。 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_CrtIsMemoryBlock**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="example"></a>例

「[_CrtIsValidHeapPointer](crtisvalidheappointer.md)」のトピックの例を参照してください。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
