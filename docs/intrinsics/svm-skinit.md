---
description: '詳細については、次を参照してください: __svm_skinit'
title: __svm_skinit
ms.date: 09/02/2019
f1_keywords:
- __svm_skinit
helpviewer_keywords:
- SKINIT instruction
- __svm_skinit intrinsic
ms.assetid: 787ec781-4cf2-40a2-aa20-5192334b131a
ms.openlocfilehash: dd35566664a6bff4a57ea986fc99ffcd731c79e2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206267"
---
# <a name="__svm_skinit"></a>__svm_skinit

**Microsoft 固有の仕様**

バーチャルマシンモニターなどの検証可能なセキュリティで保護されたソフトウェアの読み込みを開始します。

## <a name="syntax"></a>構文

```C
void __svm_skinit(
   int block_address
);
```

### <a name="parameters"></a>パラメーター

*block_address*\
64 k バイトセキュアローダーブロック (SLB) の32ビット物理アドレス。

## <a name="remarks"></a>解説

`__svm_skinit` 関数は `SKINIT` マシン語命令と同じです。 この機能は、プロセッサとトラステッドプラットフォームモジュール (TPM) を使用して、 *セキュリティカーネル* (SK) と呼ばれる信頼されたソフトウェアの検証と読み込みを行うセキュリティシステムの一部です。 仮想マシンモニターは、セキュリティカーネルの一例です。 セキュリティシステムは、初期化プロセス中に読み込まれたプログラムコンポーネントを検証します。 割り込み、デバイスアクセス、またはコンピューターがマルチプロセッサの場合、別のプログラムによって、コンポーネントの改ざんを防ぐことができます。

*Block_address* パラメーターは、 *Secure Loader block* (SLB) と呼ばれる 64 k のメモリブロックの物理アドレスを指定します。 SLB には、 *セキュアローダー* と呼ばれるプログラムが含まれています。 コンピューターの運用環境を確立し、セキュリティカーネルを読み込みます。

この関数は、ホストの仮想マシンのモニターと、ゲスト オペレーティング システムとそのアプリケーションとの対話をサポートします。 詳細については、 [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) サイトの「AMD64 アーキテクチャプログラマーの手動ボリューム 2: システムプログラミング」を検索してください。

## <a name="requirements"></a>要件

|Intrinsic|アーキテクチャ|
|---------------|------------------|
|`__svm_skinit`|x86、x64|

**ヘッダー ファイル** \<intrin.h>

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)
