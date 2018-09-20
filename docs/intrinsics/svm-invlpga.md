---
title: _ _svm_invlpga |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_invlpga
dev_langs:
- C++
helpviewer_keywords:
- __svm_invlpga intrinsic
- INVLPGA instruction
ms.assetid: aa6578ce-8278-464b-8815-a0fc45330915
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3fa5655911366b0adf21618ec7be7eeccdca9c5a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401914"
---
# <a name="svminvlpga"></a>__svm_invlpga

**Microsoft 固有の仕様**

コンピューターの変換ルックア サイド バッファーのアドレスのマッピング エントリを無効にします。 パラメーターは、仮想アドレスとを無効にするページのアドレス空間の識別子を指定します。

## <a name="syntax"></a>構文

```
void __svm_invlpga(void *Va, int ASID);
```

#### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Va*|[in]無効にするページの仮想アドレス。|
|*ASID*|[in]無効にするページのアドレス空間識別子 (ASID)。|

## <a name="remarks"></a>Remarks

`__svm_invlpga`関数は、`INVLPGA`マシン語命令。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、検索、ドキュメントでは、"AMD64 アーキテクチャ プログラマーズ手動ボリューム 2: システム プログラミングでは、"ドキュメント番号 24593、3.11、リビジョン、 [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/)サイト。

## <a name="requirements"></a>要件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__svm_invlpga`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)