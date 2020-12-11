---
description: 詳細については、「プロパティページの指定」を参照してください。
title: プロパティページの指定 (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- ISpecifyPropertyPages method
- property pages, specifying
ms.assetid: ee8678cf-c708-49ab-b0ad-fc2db31f1ac3
ms.openlocfilehash: 171440dde11178c85d1f636874b0b161691cb9cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157426"
---
# <a name="specifying-property-pages"></a>プロパティページの指定

ActiveX コントロールを作成するときは、多くの場合、コントロールのプロパティを設定するために使用できるプロパティページに関連付ける必要があります。 コントロールコンテナーでは、インターフェイスを使用し `ISpecifyPropertyPages` て、コントロールのプロパティを設定するために使用できるプロパティページを確認します。 コントロールにこのインターフェイスを実装する必要があります。

ATL を使用してを実装するには `ISpecifyPropertyPages` 、次の手順を実行します。

1. [ISpecifyPropertyPagesImpl](../atl/reference/ispecifypropertypagesimpl-class.md)からクラスを派生させます。

1. のエントリを `ISpecifyPropertyPages` クラスの COM マップに追加します。

1. コントロールに関連付けられている各ページのプロパティマップに [PROP_PAGE](reference/property-map-macros.md#prop_page) エントリを追加します。

> [!NOTE]
> [ATL コントロールウィザード](../atl/reference/atl-control-wizard.md)を使用して標準コントロールを生成する場合は、プロパティマップに PROP_PAGE エントリを追加するだけで済みます。 ウィザードによって、他の手順に必要なコードが生成されます。

適切に動作するコンテナーは、プロパティマップの PROP_PAGE エントリと同じ順序で、指定されたプロパティページを表示します。 一般に、標準のプロパティページエントリは、プロパティマップ内のカスタムページのエントリの後に配置する必要があります。これにより、ユーザーがコントロールに固有のページを最初に表示できるようになります。

## <a name="example"></a>例

Calendar コントロールの次のクラスは、インターフェイスを使用して、 `ISpecifyPropertyPages` カスタムの日付ページと株価のページを使用してプロパティを設定できることをコンテナーに通知します。

[!code-cpp[NVC_ATL_Windowing#72](../atl/codesnippet/cpp/specifying-property-pages_1.h)]

## <a name="see-also"></a>関連項目

[[プロパティ ページ]](../atl/atl-com-property-pages.md)<br/>
[ATLPages の例](../overview/visual-cpp-samples.md)
