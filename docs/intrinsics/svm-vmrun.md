---
title: __svm_vmrun
ms.date: 11/04/2016
f1_keywords:
- __svm_vmrun
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
ms.openlocfilehash: 40e53b2ebd54fc109b47f3067e5f89ce50b327de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390205"
---
# <a name="svmvmrun"></a>__svm_vmrun

**Microsoft 固有の仕様**

指定された仮想マシン制御ブロック (VMCB) に対応する仮想マシンのゲスト コードの実行を開始します。

## <a name="syntax"></a>構文

```
void __svm_vmrun(
   size_t VmcbPhysicalAddress
);
```

#### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*VmcbPhysicalAddress*|[in]VMCB の物理アドレス。|

## <a name="remarks"></a>Remarks

`__svm_vmrun`関数は、仮想マシンのゲスト コードの実行を開始するため、VMCB で最小限の情報を使用します。 使用して、 [_ _svm_vmsave](../intrinsics/svm-vmsave.md)または[_ _svm_vmload](../intrinsics/svm-vmload.md)関数の詳細については複雑な割り込みを処理するか、別のゲストに切り替える必要がある場合。

`__svm_vmrun` 関数は `VMRUN` マシン語命令と同じです。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、検索、ドキュメントでは、"AMD64 アーキテクチャ プログラマーズ手動ボリューム 2。システムは、プログラミング"文書番号 24593、リビジョン 3.11 またはそれ以降で、 [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/)サイト。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__svm_vmrun`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)<br/>
[__svm_vmsave](../intrinsics/svm-vmsave.md)<br/>
[__svm_vmload](../intrinsics/svm-vmload.md)