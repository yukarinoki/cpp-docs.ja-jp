---
title: __nop
ms.date: 11/04/2016
f1_keywords:
- __nop
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
ms.openlocfilehash: 1e76110c1ef0c4b98c295578189eedc99d76eeb9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396627"
---
# <a name="nop"></a>__nop

**Microsoft 固有の仕様**

操作を実行プラットフォームに固有のマシン語コードを生成しません。

## <a name="syntax"></a>構文

```
void __nop();
```

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__nop`|x86、ARM、x64、ARM64|

**ヘッダー ファイル** \<intrin.h >

**Microsoft 固有の仕様はここまで**

## <a name="remarks"></a>Remarks

`__nop` 関数は `NOP` マシン語命令と同じです。 X86 と x64 の詳細については、ドキュメントの検索"Intel アーキテクチャ ソフトウェア デベロッパーズ マニュアル、ボリューム 2。命令の参照を設定、"で、 [Intel Corporation](https://software.intel.com/articles/intel-sdm)サイト。

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[__noop](../intrinsics/noop.md)
