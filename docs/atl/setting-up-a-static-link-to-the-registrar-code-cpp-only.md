---
title: レジストラー コード (C++ のみ) に静的にリンクの設定
ms.date: 11/04/2016
helpviewer_keywords:
- statically linking to ATL Registrar code
- linking [C++], to ATL Registrar code
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
ms.openlocfilehash: e5f09ce4626e030c43ecc30ca44d1ac738341c6c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557410"
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>レジストラー コード (C++ のみ) に静的にリンクの設定

C++ クライアントは、レジストラーのコードに静的にリンクを作成できます。 レジストラーのパーサーの静的リンクは、リリース ビルドに約 5 K を追加します。

静的リンクを設定する最も簡単な方法は、指定した前提としています。[代入](reference/registry-macros.md#declare_registry_resourceid)オブジェクトの宣言でします。 (これは、ATL で使用される既定の指定)

## <a name="to-create-a-static-link-using-declareregistryresourceid"></a>代入を使用して静的リンクを作成するには

1. 指定[/D](../build/reference/d-preprocessor-definitions.md) `_ATL_STATIC_REGISTRY` /D ではなく **_ATL_DLL**します。

1. 再コンパイルします。

## <a name="see-also"></a>関連項目

[レジストリ コンポーネント (レジストラー)](../atl/atl-registry-component-registrar.md)
