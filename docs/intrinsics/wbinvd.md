---
title: __wbinvd
ms.date: 11/04/2016
f1_keywords:
- __wbinvd
helpviewer_keywords:
- __wbinvd intrinsic
- wbinvd instruction
ms.assetid: 628d0981-39e5-49e1-bd43-706d123af121
ms.openlocfilehash: 99c7a452e063dea328e4aa1362aae8783929deb0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59039268"
---
# <a name="wbinvd"></a>__wbinvd

**Microsoft 固有の仕様**

書き戻しとキャッシュの無効化が生成されます (`wbinvd`) 命令。

## <a name="syntax"></a>構文

```
void __wbinvd(void);
```

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__wbinvd`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

この関数は、0 の特権レベル (CPL) でのカーネル モードで使用可能なのみとルーチンは組み込みとして使用できるのみです。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)