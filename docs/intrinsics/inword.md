---
title: __inword
ms.date: 09/02/2019
f1_keywords:
- __inword_cpp
- __inword
helpviewer_keywords:
- in instruction
- __inword intrinsic
ms.assetid: 5c617edd-6709-40a1-aad2-40d5e39283c6
ms.openlocfilehash: 7daaf1abd5089716061f118e30e9534e5c5c18ee
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440979"
---
# <a name="__inword"></a>__inword

**Microsoft 固有の仕様**

`in` 命令を使用して、指定されたポートからデータを読み取ります。

## <a name="syntax"></a>構文

```C
unsigned short __inword(
   unsigned short Port
);
```

### <a name="parameters"></a>パラメーター

*ポート*\
から読み取り元のポート。

## <a name="return-value"></a>戻り値

読み取られたデータの単語。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__inword`|x86、x64|

**ヘッダーファイル**\<に存在します。 h >

## <a name="remarks"></a>コメント

このルーチンは、組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
