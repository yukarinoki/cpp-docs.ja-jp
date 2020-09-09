---
title: レジストラー コードに静的リンクを設定する (C++ のみ)
description: C++ コードを ATL レジストラーコードに静的にリンクする方法。
ms.date: 09/03/2020
helpviewer_keywords:
- statically linking to ATL Registrar code
- linking [C++], to ATL Registrar code
ms.assetid: 835f5885-87a6-48fa-91e6-60988ee65538
ms.openlocfilehash: f08f7d9433ae1344c7a98a5c52502d03bad21e91
ms.sourcegitcommit: 0df2b7ab4e81284c5248e4584767591dcc1950c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "89609159"
---
# <a name="setting-up-a-static-link-to-the-registrar-code-c-only"></a>レジストラーコードへの静的リンクの設定 (C++ のみ)

C++ クライアントは、レジストラーのコードへの静的なリンクを作成できます。 レジストラーのパーサーの静的なリンクは、リリースビルドに約5K を追加します。

静的リンクを設定する最も簡単な方法は、オブジェクトの宣言でを指定していることを前提としてい [`DECLARE_REGISTRY_RESOURCEID`](reference/registry-macros.md#declare_registry_resourceid) ます。 (これは ATL によって使用される既定の仕様です)。

## <a name="to-create-a-static-link-using-declare_registry_resourceid"></a>を使用して静的リンクを作成するには `DECLARE_REGISTRY_RESOURCEID`

1. **`/D _ATL_STATIC_REGISTRY`** **`/D _ATL_DLL`** CL コマンドラインで、の代わりにを指定します。 詳細については、「[`/D`](../build/reference/d-preprocessor-definitions.md)」を参照してください。

1. Recompile.

## <a name="see-also"></a>関連項目

[レジストリコンポーネント (レジストラー)](../atl/atl-registry-component-registrar.md)
