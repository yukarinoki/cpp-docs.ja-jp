---
description: '詳細については、次を参照してください: _enable'
title: _enable
ms.date: 09/02/2019
f1_keywords:
- _enable
- _enable_cpp
helpviewer_keywords:
- enable intrinsic
- _enable intrinsic
- ssm instruction
ms.assetid: 8bee669b-6bd8-4e25-9383-bb7d57295b4d
ms.openlocfilehash: b9c84a31869dd356d5ee6ebd4eae5bd579cf319e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337043"
---
# <a name="_enable"></a>_enable

**Microsoft 固有の仕様**

割り込みを有効にします。

## <a name="syntax"></a>構文

```C
void _enable(void);
```

## <a name="requirements"></a>必要条件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`_enable`|x86、ARM、x64、ARM64|

**ヘッダー ファイル** \<intrin.h>

## <a name="remarks"></a>解説

`_enable` は、プロセッサに対して割り込みフラグを設定するように指示します。 x86 システムでは、この関数は割り込みフラグの設定 (`sti`) 命令を生成します。

この関数はカーネル モードのみで使用できます。 ユーザー モードで使用した場合は、特権命令例外がスローされます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
