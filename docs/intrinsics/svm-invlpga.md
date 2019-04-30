---
title: __svm_invlpga
ms.date: 11/04/2016
f1_keywords:
- __svm_invlpga
helpviewer_keywords:
- __svm_invlpga intrinsic
- INVLPGA instruction
ms.assetid: aa6578ce-8278-464b-8815-a0fc45330915
ms.openlocfilehash: 5e470fc12ad47aa156c513b293543fa356398d5e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390270"
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

`__svm_invlpga` 関数は `INVLPGA` マシン語命令と同じです。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、検索、ドキュメントでは、"AMD64 アーキテクチャ プログラマーズ手動ボリューム 2。文書番号 24593、3.11、リビジョンのシステム プログラミング、"、 [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/)サイト。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`__svm_invlpga`|x86、x64|

**ヘッダー ファイル** \<intrin.h >

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)