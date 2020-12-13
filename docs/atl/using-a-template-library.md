---
description: 詳細については、「テンプレートライブラリの使用」を参照してください。
title: テンプレートライブラリの使用 (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- template libraries
ms.assetid: 5e80ec6e-a61c-41ce-b34b-9a6252c46265
ms.openlocfilehash: 46f1f6fd418b64bcced09f86ea55c95462f2dfee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138230"
---
# <a name="using-a-template-library"></a>テンプレートライブラリの使用

テンプレートは、マクロに似ています。 マクロと同様に、テンプレートを呼び出すと、記述したコードに対して (適切なパラメーターの置換によって) 拡張されます。 ただし、テンプレートは、パラメーターとして渡す型に基づいて新しいクラスを作成できるようにするために、これよりも先に進みます。 これらの新しいクラスは、テンプレートコードで表現された操作を実行するタイプセーフな方法を実装します。

ATL などのテンプレートライブラリは、通常、ソースコードとしてのみ提供される (または、サポートされる実行時間が短いソースコードとして) 指定されており、本質的には階層構造ではありません。 クラスから派生させて必要な機能を取得するのではなく、テンプレートからクラスをインスタンス化します。

## <a name="see-also"></a>関連項目

[ATL の概要](../atl/introduction-to-atl.md)
