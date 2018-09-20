---
title: __inwordstring | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __inwordstring
- __inwordstring_cpp
dev_langs:
- C++
helpviewer_keywords:
- __inwordstring intrinsic
- rep insw instruction
ms.assetid: 6de37939-017a-4740-9e3d-7de78a30daba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 969d57d01915ecfcf20c29b08d71c438206c45b8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440531"
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

*Buffer*<br/>
[out]ここでは、ポートから読み取ったデータを書き込まれます。

*カウント*<br/>
[in]読み取るデータの文字数です。

## <a name="requirements"></a>要件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__inwordstring`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

このルーチンは、組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)