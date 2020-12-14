---
description: '詳細については、次を参照してください: __svm_invlpga'
title: __svm_invlpga
ms.date: 09/02/2019
f1_keywords:
- __svm_invlpga
helpviewer_keywords:
- __svm_invlpga intrinsic
- INVLPGA instruction
ms.assetid: aa6578ce-8278-464b-8815-a0fc45330915
ms.openlocfilehash: dc976f535381fcfdfec0da5c1a280c4df281c114
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314751"
---
# <a name="__svm_invlpga"></a>__svm_invlpga

**Microsoft 固有の仕様**

コンピューターの変換の検索用バッファーのアドレスマッピングエントリを無効にします。 無効にするページの仮想アドレスとアドレス空間識別子をパラメーターで指定します。

## <a name="syntax"></a>構文

```C
void __svm_invlpga(void *Vaddr, int as_id);
```

### <a name="parameters"></a>パラメーター

*Vaddr*\
から無効化するページの仮想アドレス。

*as_id*\
から無効化するページのアドレス空間識別子 (ASID)。

## <a name="remarks"></a>解説

`__svm_invlpga` 関数は `INVLPGA` マシン語命令と同じです。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、 [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) サイトのドキュメント「AMD64 アーキテクチャプログラマーの手動ボリューム 2: システムプログラミング」、「ドキュメント番号24593、リビジョン3.11」を検索してください。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__svm_invlpga`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
