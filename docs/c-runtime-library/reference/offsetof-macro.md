---
title: offsetof マクロ
ms.date: 11/04/2016
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
- offsetof
helpviewer_keywords:
- structure members, offset
- offsetof macro
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
ms.openlocfilehash: a0f367dbe6fa2681a7d413304f32b5699b8f7cee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156070"
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

**offsetof**親データ構造体の先頭から指定されたメンバーのバイト オフセットを返します。 ビット フィールドには定義されません。

## <a name="remarks"></a>Remarks

**Offsetof**マクロのバイト オフセットを返します*memberName*によって指定された構造体の先頭から*structName*型の値として**size_t**します。 型を指定することができます、**構造体**キーワード。

> [!NOTE]
> **offsetof**関数ではないと、C のプロトタイプを使用して説明することはできません。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**offsetof**|\<stddef.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="see-also"></a>関連項目

[メモリ割り当て](../../c-runtime-library/memory-allocation.md)<br/>
