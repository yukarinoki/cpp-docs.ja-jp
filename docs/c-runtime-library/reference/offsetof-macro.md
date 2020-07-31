---
title: offsetof マクロ
ms.date: 11/04/2016
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- offsetof
helpviewer_keywords:
- structure members, offset
- offsetof macro
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
ms.openlocfilehash: ee6d5e56bb9f41a842e53984f754c7c07d58a125
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213503"
---
# <a name="offsetof-macro"></a>offsetof マクロ

親構造体の先頭からメンバーのオフセットを取得します。

## <a name="syntax"></a>構文

```C
size_t offsetof(
   structName,
   memberName
);
```

### <a name="parameters"></a>パラメーター

*structName*<br/>
親データ構造体の名前。

*memberName*<br/>
オフセットを決定する親データ構造体のメンバーの名前。

## <a name="return-value"></a>戻り値

**offsetof**は、親データ構造体の先頭から、指定されたメンバーのオフセットをバイト単位で返します。 ビット フィールドには定義されません。

## <a name="remarks"></a>解説

**Offsetof**マクロは、 *structName*によって指定された構造*体の先頭から* **size_t**型の値としてオフセットをバイト単位で返します。 キーワードを使用して型を指定でき **`struct`** ます。

> [!NOTE]
> **offsetof**は関数ではなく、C プロトタイプを使用して記述することはできません。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**offsetof**|\<stddef.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="see-also"></a>関連項目

[メモリの割り当て](../../c-runtime-library/memory-allocation.md)<br/>
