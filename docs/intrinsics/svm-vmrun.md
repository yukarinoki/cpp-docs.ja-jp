---
description: '詳細については、次を参照してください: __svm_vmrun'
title: __svm_vmrun
ms.date: 09/02/2019
f1_keywords:
- __svm_vmrun
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
ms.openlocfilehash: c01716e496513aa11132fdfc95235a39c7277279
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333701"
---
# <a name="__svm_vmrun"></a>__svm_vmrun

**Microsoft 固有の仕様**

指定された仮想マシン制御ブロック (VMCB) に対応する仮想マシンのゲストコードの実行を開始します。

## <a name="syntax"></a>構文

```C
void __svm_vmrun(
   size_t VmcbPhysicalAddress
);
```

### <a name="parameters"></a>パラメーター

*VmcbPhysicalAddress*\
からVMCB の物理アドレス。

## <a name="remarks"></a>解説

関数は、 `__svm_vmrun` 仮想マシンのゲストコードの実行を開始するために、VMCB 内の最小限の情報を使用します。 複雑な割り込みを処理したり、別のゲストに切り替えたりするために詳細情報が必要な場合は、 [__svm_vmsave](../intrinsics/svm-vmsave.md) または [__svm_vmload](../intrinsics/svm-vmload.md) 関数を使用します。

`__svm_vmrun` 関数は `VMRUN` マシン語命令と同じです。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、 [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) サイトのドキュメント「AMD64 アーキテクチャプログラマーの手動ボリューム 2: システムプログラミング」、「ドキュメント番号24593、リビジョン3.11 以降」を検索してください。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__svm_vmrun`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[__svm_vmsave](../intrinsics/svm-vmsave.md)\
[__svm_vmload](../intrinsics/svm-vmload.md)
