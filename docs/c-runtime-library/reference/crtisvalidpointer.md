---
title: _CrtIsValidPointer
ms.date: 11/04/2016
apiname:
- _CrtIsValidPointer
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
- CrtlsValidPointer
- _CrtIsValidPointer
helpviewer_keywords:
- CrtIsValidPointer function
- _CrtIsValidPointer function
ms.assetid: 91c35590-ea5e-450f-a15d-ad8d62ade1fa
ms.openlocfilehash: 64197d460cdb7dd26d22196c08151be09df48573
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429249"
---
# <a name="crtisvalidpointer"></a>_CrtIsValidPointer

ポインターが null でないことを確認します。 Visual Studio 2010 より前のバージョンの C ランタイム ライブラリでは、指定したメモリ範囲で読み取りおよび書き込みが可能であることを確認します (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
int _CrtIsValidPointer(
   const void *address,
   unsigned int size,
   int access
);
```

### <a name="parameters"></a>パラメーター

*address*<br/>
確認のためにテストするメモリ範囲の先頭を指します。

*size*<br/>
指定されたメモリ範囲のサイズ (バイト単位)。

*access*<br/>
メモリ範囲に対して確認する読み取り/書き込みアクセシビリティ。

## <a name="return-value"></a>戻り値

**_CrtIsValidPointer**指定したポインターが null でない場合は TRUE を返します。 Visual Studio 2010 より前のバージョンの CRT ライブラリでは、メモリ範囲で指定された操作が有効である場合に、TRUE を返します。 それ以外の場合、関数は FALSE を返します。

## <a name="remarks"></a>Remarks

Visual Studio 2010 では、CRT ライブラリ以降、*サイズ*と*アクセス*パラメーターは無視されますと **_CrtIsValidPointer**だけのことを確認します指定*アドレス*が null でないです。 このテストは自分で簡単に実行できるので、この関数を使用することはお勧めしません。 Visual Studio 2010 以前のバージョンでは、関数は、検証が行われますから始まるメモリ範囲*アドレス*の拡張と*サイズ*バイトは、指定されたアクセシビリティ操作に対して有効です。 ときに*アクセス*を TRUE に設定すると、メモリ範囲で読み取りと書き込みの両方の確認されます。 ときに*アクセス*false で、メモリの範囲は読み取りだけ確認します。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない、呼び出し **_CrtIsValidPointer**プリプロセス時に削除されます。

この関数は TRUE または FALSE を返すため、[_ASSERT](assert-asserte-assert-expr-macros.md) 系マクロに渡すことによって、デバッグ用の単純なエラー処理機構を作成できます。 次の例では、メモリ範囲で読み取りと書き込みの両方が無効だった場合、アサーション エラーが発生します。

```C
_ASSERTE( _CrtIsValidPointer( address, size, TRUE ) );
```

詳細について **_CrtIsValidPointer**他のデバッグ関数およびマクロとで使用できるを参照してください[レポート用マクロ](/visualstudio/debugger/macros-for-reporting)します。 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_CrtIsValidPointer**|\<crtdbg.h>|

**_CrtIsValidPointer**は Microsoft 拡張機能です。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="example"></a>例

「[_CrtIsValidHeapPointer](crtisvalidheappointer.md)」のトピックの例を参照してください。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
