---
description: '詳細については、次を参照してください: _disable'
title: _disable
ms.date: 09/02/2019
f1_keywords:
- _disable_cpp
- _disable
helpviewer_keywords:
- _disable intrinsic
- rsm instruction
- disable intrinsic
ms.assetid: 52da3df9-815c-4524-9839-6d1742cff5c6
ms.openlocfilehash: c118315a4fea2dad401cc5c6f3621a8ec3b1794c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337094"
---
# <a name="_disable"></a>_disable

**Microsoft 固有の仕様**

割り込みを無効にします。

## <a name="syntax"></a>構文

```C
void _disable(void);
```

## <a name="requirements"></a>必要条件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`_disable`|x86、ARM、x64、ARM64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

`_disable` は、プロセッサに対して割り込みフラグをクリアするように指示します。 x86 システムでは、この関数は割り込みフラグのクリア (`cli`) 命令を生成します。

この関数はカーネル モードのみで使用できます。 ユーザー モードで使用した場合は、実行時に特権命令例外がスローされます。

ARM および ARM64 プラットフォームでは、このルーチンは組み込みとしてのみ使用できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
