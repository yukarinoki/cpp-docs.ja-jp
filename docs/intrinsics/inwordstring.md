---
title: __inwordstring
ms.date: 11/04/2016
f1_keywords:
- __inwordstring
- __inwordstring_cpp
helpviewer_keywords:
- __inwordstring intrinsic
- rep insw instruction
ms.assetid: 6de37939-017a-4740-9e3d-7de78a30daba
ms.openlocfilehash: 52c36754e1eea56b84eeb494e82e37a5b043246e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59030220"
---
# <a name="inwordstring"></a>__inwordstring

**Microsoft 固有の仕様**

使用して、指定されたポートからデータを読み取り、`rep insw`命令。

## <a name="syntax"></a>構文

```
void __inwordstring(
   unsigned short Port,
   unsigned short* Buffer,
   unsigned long Count
);
```

#### <a name="parameters"></a>パラメーター

*ポート*<br/>
[in]読み取るポート。

*バッファー*<br/>
[out]ここでは、ポートから読み取ったデータを書き込まれます。

*カウント*<br/>
[in]読み取るデータの文字数です。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__inwordstring`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

このルーチンは、組み込みとしてのみ使用できます。

**END Microsoft 固有の仕様**

## <a name="see-also"></a>関連項目

[コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)