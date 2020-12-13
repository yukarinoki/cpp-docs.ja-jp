---
description: '詳細については、次を参照してください: __svm_vmsave'
title: __svm_vmsave
ms.date: 09/02/2019
f1_keywords:
- __svm_vmsave
helpviewer_keywords:
- VMSAVE instruction
- __svm_vmsave intrinsic
ms.assetid: 617a60bd-8514-4ba1-8066-bcf4dd481030
ms.openlocfilehash: 5c0e4eb5f2d4c0f73921572811b070c8f87a2673
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333676"
---
# <a name="__svm_vmsave"></a>__svm_vmsave

**Microsoft 固有の仕様**

指定されたバーチャルマシン制御ブロック (VMCB) にプロセッサ状態のサブセットを格納します。

## <a name="syntax"></a>構文

```C
void __svm_vmsave(
   size_t VmcbPhysicalAddress
);
```

### <a name="parameters"></a>パラメーター

*VmcbPhysicalAddress*\
からVMCB の物理アドレス。

## <a name="remarks"></a>解説

`__svm_vmsave` 関数は `VMSAVE` マシン語命令と同じです。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、 [AMD Corporation](https://developer.amd.com/resources/developer-guides-manuals/) サイトのドキュメント「AMD64 アーキテクチャプログラマーの手動ボリューム 2: システムプログラミング」、「ドキュメント番号24593、リビジョン3.11 以降」を検索してください。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__svm_vmsave`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[__svm_vmrun](../intrinsics/svm-vmrun.md)\
[__svm_vmload](../intrinsics/svm-vmload.md)
