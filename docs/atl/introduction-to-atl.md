---
description: '詳細情報: ATL の概要'
title: ATL の概要
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- COM objects, creating in ATL
- ATL
ms.assetid: 77f565e8-c4ec-4a80-af4b-7278fcfe5c98
ms.openlocfilehash: 43a99dbd784b33f0595cccfa6014bdda17a2bdd1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147707"
---
# <a name="introduction-to-atl"></a>ATL の概要

ATL は、小規模で高速のコンポーネントオブジェクトモデル (COM) オブジェクトを簡単に作成できる、テンプレートベースの C++ クラスのセットである Active Template Library です。 これには、 [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)、 [IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)、 [IClassFactory2](/windows/win32/api/ocidl/nn-ocidl-iclassfactory2)、およびの `IDispatch` 2 つのインターフェイス、標準 com 列挙子インターフェイス、コネクションポイント、ティアオフインターフェイス、ActiveX コントロールなどの主要な com 機能が特別にサポートされています。

ATL コードを使用すると、シングルスレッドオブジェクト、アパートメントモデルオブジェクト、フリースレッドモデルオブジェクト、またはフリースレッドオブジェクトとアパートメントモデルオブジェクトの両方を作成できます。

このセクションでは、次のトピックについて説明します。

- [テンプレートライブラリ](../atl/using-a-template-library.md)と標準ライブラリの違いについて説明します。

- [ATL でできることとできない](../atl/scope-of-atl.md)こと。

- [ATL と MFC の選択に関する推奨事項](../atl/recommendations-for-choosing-between-atl-and-mfc.md)。

## <a name="see-also"></a>関連項目

[COM と ATL の概要](../atl/introduction-to-com-and-atl.md)
