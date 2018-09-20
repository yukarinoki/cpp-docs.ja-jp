---
title: _ _wbinvd |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __wbinvd
dev_langs:
- C++
helpviewer_keywords:
- __wbinvd intrinsic
- wbinvd instruction
ms.assetid: 628d0981-39e5-49e1-bd43-706d123af121
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a1f412de7c8752ba1c1ba1324d20e1d4fb4c6a7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388382"
---
# <a name="wbinvd"></a>__wbinvd

**Microsoft 固有の仕様**

書き戻しとキャッシュの無効化が生成されます (`wbinvd`) 命令。

## <a name="syntax"></a>構文

```
void __wbinvd(void);
```

## <a name="requirements"></a>要件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__wbinvd`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

この関数は、0 の特権レベル (CPL) でのカーネル モードで使用可能なのみとルーチンは組み込みとして使用できるのみです。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)