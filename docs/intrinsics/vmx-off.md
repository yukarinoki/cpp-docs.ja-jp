---
description: '詳細については、次を参照してください: __vmx_off'
title: __vmx_off
ms.date: 09/02/2019
f1_keywords:
- __vmx_off
helpviewer_keywords:
- VMXOFF instruction
- __vmx_off intrinsic
ms.assetid: 78a32d46-9291-406c-b982-a550855aff18
ms.openlocfilehash: d36b9079165dd68b207658d6141bdf11bd9747cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333586"
---
# <a name="__vmx_off"></a>__vmx_off

**Microsoft 固有の仕様**

プロセッサの仮想マシン拡張機能 (VMX) 操作を非アクティブにします。

## <a name="syntax"></a>構文

```C
void __vmx_off();
```

## <a name="remarks"></a>解説

`__vmx_off` 関数は `VMXOFF` マシン語命令と同じです。 この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、 [Intel Corporation](https://software.intel.com/articles/intel-sdm) サイトのドキュメント「IA-32 intel Architecture の Intel Virtualization Technical Specification」 (ドキュメント番号 C97063-002) を検索してください。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__vmx_off`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
