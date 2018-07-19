---
title: レジストラー コード (C++ のみ) への静的リンクの設定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- statically linking to ATL Registrar code
- linking [C++], to ATL Registrar code
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dca93c8f0fcae578700a9d9970977179fbd142d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360189"
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>レジストラー コード (C++ のみ) への静的リンクを設定します。
C++ のクライアントは、レジストラーのコードに静的なリンクを作成できます。 リリース ビルドを約 5 K を追加、レジストラーのパーサーの静的にリンクします。  
  
 静的リンクを設定する最も簡単な方法は、指定した前提としています。[代入](reference/registry-macros.md#declare_registry_resourceid)オブジェクトの宣言でします。 (これは、ATL で使用される既定の指定)  
  
### <a name="to-create-a-static-link-using-declareregistryresourceid"></a>代入を使用して静的なリンクを作成するには  
  
1.  指定[/D](../build/reference/d-preprocessor-definitions.md) `_ATL_STATIC_REGISTRY` /D ではなく **_ATL_DLL**です。  
  
2.  再コンパイルします。  
  
## <a name="see-also"></a>関連項目  
 [レジストリ コンポーネント (レジストラー)](../atl/atl-registry-component-registrar.md)

