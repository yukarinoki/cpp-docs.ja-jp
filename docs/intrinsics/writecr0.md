---
title: __writecr0 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _writecr0
dev_langs:
- C++
helpviewer_keywords:
- _writecr0 intrinsic
ms.assetid: a143d08d-0333-4e1b-91b4-4acb2ae91b5a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5542dc1c4aeff873f14d8ab9498025c8852dfbd9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409312"
---
# <a name="writecr0"></a>__writecr0

**Microsoft 固有の仕様**

値を書き込みます`Data`CR0 レジスタにします。

## <a name="syntax"></a>構文

```
void writecr0( 
   unsigned __int64 Data 
);
```

#### <a name="parameters"></a>パラメーター

*データ*<br/>
[in]CR0 レジスタに書き込む値。

## <a name="requirements"></a>要件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__writecr0`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

この組み込みはカーネル モードのみで使用でき、そのルーチンは組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)