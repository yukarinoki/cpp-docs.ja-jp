---
title: _disable
ms.date: 11/04/2016
f1_keywords:
- _disable_cpp
- _disable
helpviewer_keywords:
- _disable intrinsic
- rsm instruction
- disable intrinsic
ms.assetid: 52da3df9-815c-4524-9839-6d1742cff5c6
ms.openlocfilehash: 93db063c6b53f0bec739ba134728b83379a21f53
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024680"
---
# <a name="disable"></a>_disable

**Microsoft 固有の仕様**

割り込みを無効にします。

## <a name="syntax"></a>構文

```
void _disable(void);
```

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`_disable`|x86、ARM、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

`_disable` は、プロセッサに対して割り込みフラグをクリアするように指示します。 x86 システムでは、この関数は割り込みフラグのクリア (`cli`) 命令を生成します。

この関数はカーネル モードのみで使用できます。 ユーザー モードで使用した場合は、実行時に特権命令例外がスローされます。

ARM プラットフォームでは、このルーチンは組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)