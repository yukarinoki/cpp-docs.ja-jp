---
description: '詳細については、次を参照してください: __svm_vmload'
title: __svm_vmload
ms.date: 09/02/2019
f1_keywords:
- __svm_vmload
helpviewer_keywords:
- __svm_vmload intrinsic
- VMLOAD instruction
ms.assetid: b46a5592-db76-4ffc-8694-2f3494e28bed
ms.openlocfilehash: 975f6aed50007b0b184bbab2b9b48790e5e20616
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333714"
---
# <a name="__svm_vmload"></a>__svm_vmload

**Microsoft 固有の仕様**

指定されたバーチャルマシン制御ブロック (VMCB) からプロセッサ状態のサブセットを読み込みます。

## <a name="syntax"></a>構文

```C
void __svm_vmload(
   size_t VmcbPhysicalAddress
);
```

### <a name="parameters"></a>パラメーター

*VmcbPhysicalAddress*\
からVMCB の物理アドレス。

## <a name="remarks"></a>解説

`__svm_vmload` 関数は `VMLOAD` マシン語命令と同じです。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、 [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) サイトのドキュメント「AMD64 アーキテクチャプログラマーの手動ボリューム 2: システムプログラミング」、「ドキュメント番号24593、リビジョン3.11」を検索してください。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__svm_vmload`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)\
[__svm_vmrun](../intrinsics/svm-vmrun.md)\
[__svm_vmsave](../intrinsics/svm-vmsave.md)
