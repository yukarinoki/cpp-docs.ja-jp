---
title: _enable
ms.date: 11/04/2016
f1_keywords:
- _enable
- _enable_cpp
helpviewer_keywords:
- enable intrinsic
- _enable intrinsic
- ssm instruction
ms.assetid: 8bee669b-6bd8-4e25-9383-bb7d57295b4d
ms.openlocfilehash: e1ece6d6f4040b81b55d8400407d46f165b56b53
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349031"
---
# <a name="enable"></a>_enable

**Microsoft 固有の仕様**

割り込みを有効にします。

## <a name="syntax"></a>構文

```
void _enable(void);
```

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`_enable`|x86、ARM、x64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

`_enable` は、プロセッサに対して割り込みフラグを設定するように指示します。 x86 システムでは、この関数は割り込みフラグの設定 (`sti`) 命令を生成します。

この関数はカーネル モードのみで使用できます。 ユーザー モードで使用した場合は、特権命令例外がスローされます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)