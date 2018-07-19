---
title: _CrtIsMemoryBlock | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _CrtIsMemoryBlock function
- CrtIsMemoryBlock function
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 45331186cca5aab3c7971ba404d7b6da98139130
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2018
ms.locfileid: "34450733"
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

*UserData*<br/>
検査するメモリ ブロックの先頭へのポインター。

*size*<br/>
指定されたブロックのサイズ (バイト)。

*requestNumber*<br/>
ブロックの割り当て番号へのポインターまたは**NULL**です。

*ファイル名*<br/>
ブロックを要求したソース ファイルの名前へのポインターまたは**NULL**です。

*行番号*<br/>
ソース ファイル内の行番号へのポインターまたは**NULL**です。

## <a name="return-value"></a>戻り値

**_CrtIsMemoryBlock**返します**TRUE**指定されたメモリ ブロックがローカル ヒープ内にあり、有効なデバッグ ヒープ ブロック型識別子です。 それ以外の場合、関数を返します**FALSE**です。

## <a name="remarks"></a>コメント

**_CrtIsMemoryBlock**関数は、指定されたメモリ ブロックがアプリケーションのローカル ヒープ内にあることと、有効なブロック型識別子があることを確認します。 また、この関数を使用すると、オブジェクト割り当て順序番号と、メモリ ブロックの割り当て要求を行ったソース ファイル名および行番号を取得できます。 渡す以外**NULL**の値を*requestNumber*、 *filename*、または*linenumber*パラメーター原因 **_CrtIsMemoryBlock**ブロックがローカル ヒープ内が見つかった場合、メモリ ブロックのデバッグ ヘッダーの値にこれらのパラメーターを設定します。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていないへの呼び出し **_CrtIsMemoryBlock**プリプロセス時に削除されます。

場合 **_CrtIsMemoryBlock**失敗すると、それを返します**FALSE**出力パラメーターは、既定値に初期化されます*requestNumber*と**lineNumber。** を 0 に設定し、 *filename*に設定されている**NULL**です。

この関数は **TRUE** または **FALSE** を返すため、[_ASSERT](assert-asserte-assert-expr-macros.md) 系マクロに渡すことによって、デバッグ用の単純なエラー処理機構を作成できます。 指定されたアドレスがローカル ヒープ内にない場合に、アサーションの失敗を発生させるには、次のように記述します。

```C
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,
          &filename, &linenumber ) );
```

方法の詳細についての **_CrtIsMemoryBlock**他のデバッグ関数およびマクロと共に使用するを参照してください[レポート用マクロ](/visualstudio/debugger/macros-for-reporting)です。 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_CrtIsMemoryBlock**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="example"></a>例

「[_CrtIsValidHeapPointer](crtisvalidheappointer.md)」のトピックの例を参照してください。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
