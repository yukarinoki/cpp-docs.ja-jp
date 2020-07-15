---
title: /DYNAMICBASE
ms.date: 06/12/2018
f1_keywords:
- /dynamicbase
helpviewer_keywords:
- -DYNAMICBASE editbin option
- DYNAMICBASE editbin option
- /DYNAMICBASE editbin option
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
ms.openlocfilehash: 54644d9df546299be3b688f9745a121592938df6
ms.sourcegitcommit: 31a443c9998cf5cfbaff00fcf815b133f55b2426
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "86373620"
---
# <a name="dynamicbase"></a>/DYNAMICBASE

読み込み時にランダムに再配置できる実行可能イメージを生成するかどうかを指定します。これは、Windows Vista で初めて利用可能になった Windows のアドレス空間レイアウトランダム化 (ASLR) 機能を使用して行います。

## <a name="syntax"></a>Syntax

> **/DYNAMICBASE**[**: NO**]

## <a name="remarks"></a>解説

**/DYNAMICBASE**オプションは、*実行可能イメージ*(.dll または .exe ファイル) のヘッダーを変更して、読み込み時にアプリケーションをランダムに再配置する必要があるかどうかを示し、仮想アドレス割り当てのランダム化を有効にします。これは、ヒープ、スタック、およびその他のオペレーティングシステムの割り当ての仮想メモリ位置に影響します。 **/DYNAMICBASE**オプションは、32ビットイメージと64ビットイメージの両方に適用されます。 ASLR は、Windows Vista 以降のオペレーティングシステムでサポートされています。 このオプションは、以前のオペレーティングシステムでは無視されます。

既定では、 **/DYNAMICBASE**は有効になっています。 このオプションを無効にするには、 **/DYNAMICBASE: NO**を使用します。 [/HIGHENTROPYVA](highentropyva-support-64-bit-aslr.md)オプションが効果を持つようにするには、 **/DYNAMICBASE**オプションを指定する必要があります。

## <a name="see-also"></a>関連項目

- [EDITBIN オプション](editbin-options.md)
- [Windows ISV ソフトウェアセキュリティ防御](https://docs.microsoft.com/previous-versions/bb430720(v=msdn.10))
