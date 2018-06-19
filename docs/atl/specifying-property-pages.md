---
title: プロパティ ページ (ATL) を指定する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- ISpecifyPropertyPages
dev_langs:
- C++
helpviewer_keywords:
- ISpecifyPropertyPages method
- property pages, specifying
ms.assetid: ee8678cf-c708-49ab-b0ad-fc2db31f1ac3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e8d4cbeaa8ea9a57f9287f2d2fe78c61884ba4a3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358926"
---
# <a name="specifying-property-pages"></a>プロパティ ページを指定します。
ActiveX コントロールを作成するときに多くの場合に、コントロールのプロパティを設定するために使用するプロパティ ページに関連付けます。 コンテナーの使用を制御する、 **ISpecifyPropertyPages**インターフェイスについては、コントロールのプロパティを設定するプロパティ ページを使用できます。 コントロールにこのインターフェイスを実装する必要があります。  
  
 実装する**ISpecifyPropertyPages** ATL を使用して、次の手順を実行します。  
  
1.  クラスを派生[ISpecifyPropertyPagesImpl](../atl/reference/ispecifypropertypagesimpl-class.md)です。  
  
2.  エントリを追加**ISpecifyPropertyPages**クラスの COM マップにします。  
  
3.  追加、 [PROP_PAGE](reference/property-map-macros.md#prop_page)コントロールに関連付けられている各ページのプロパティ マップへのエントリ。  
  
> [!NOTE]
>  標準コントロールを使用して、生成するときに、 [ATL コントロール ウィザード](../atl/reference/atl-control-wizard.md)、のみを追加する必要が、`PROP_PAGE`プロパティ マップのエントリ。 ウィザードでは、必要な手順については、その他のコードを生成します。  
  
 正常なコンテナーと同じ順序で指定のプロパティ ページが表示されます、`PROP_PAGE`プロパティ マップのエントリ。 一般に、ユーザーが最初に、コントロールに固有のページを参照しているためは、マップでは、プロパティ、カスタム ページのエントリ後に標準のプロパティ ページのエントリを配置する必要があります。  
  
## <a name="example"></a>例  
 予定表の次のクラスが使用を制御、 **ISpecifyPropertyPages**インターフェイスへのカスタムの日付 ページおよびストックの色 ページを使用してそのプロパティを設定できるコンテナーを通知します。  
  
 [!code-cpp[NVC_ATL_Windowing#72](../atl/codesnippet/cpp/specifying-property-pages_1.h)]  
  
## <a name="see-also"></a>関連項目  
 [プロパティ ページ](../atl/atl-com-property-pages.md)   
 [例](../visual-cpp-samples.md)

