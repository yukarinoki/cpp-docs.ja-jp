---
description: '詳細情報: ATL COM プロパティページ'
title: ATL COM プロパティ ページ
ms.date: 11/04/2016
helpviewer_keywords:
- property pages, COM
- ATL COM objects
- COM property pages
- property pages, ATL
- COM objects, ATL
- ATL property pages
ms.assetid: 663c7caa-2e5e-4b5c-b8ea-fd434ceb1654
ms.openlocfilehash: 252e8a98f4f34a07a374c77fc48aacd7eee8969f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165980"
---
# <a name="atl-com-property-pages"></a>ATL COM プロパティ ページ

COM プロパティページには、1つまたは複数の COM オブジェクトのプロパティ (またはメソッドの呼び出し) を設定するためのユーザーインターフェイスが用意されています。 プロパティページは、ActiveX コントロールによって広く使用され、デザイン時にコントロールプロパティを設定するための豊富なユーザーインターフェイスを提供します。

プロパティページは、 [IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) インターフェイスまたは [IPropertyPage2](/windows/win32/api/ocidl/nn-ocidl-ipropertypage2) インターフェイスを実装する COM オブジェクトです。 これらのインターフェイスは、ページを (ページのコンテナーを表す COM オブジェクト) と関連付けられるようにするメソッド `site` を提供します。また、プロパティページのユーザーによって行われた変更に応じて、メソッドが呼び出される com *オブジェクトも* 含まれます。 プロパティページコンテナーは、プロパティページインターフェイスのメソッドを呼び出して、ユーザーインターフェイスを表示または非表示にするタイミングと、ユーザーによって行われた変更を基になるオブジェクトに適用するタイミングを指定します。

各プロパティページは、プロパティを設定できるオブジェクトとは関係なく、完全にビルドできます。 プロパティページで必要とされるのは、特定のインターフェイス (またはインターフェイスのセット) を理解し、そのインターフェイスでメソッドを呼び出すためのユーザーインターフェイスを提供することだけです。

詳細については、「Windows SDK の [プロパティシートとプロパティページ](/windows/win32/com/property-sheets-and-property-pages) 」を参照してください。

## <a name="in-this-section"></a>このセクションの内容

[プロパティページの指定](../atl/specifying-property-pages.md)<br/>
コントロールのプロパティページを指定する手順を示し、クラスの例を示します。

[プロパティページの実装](../atl/implementing-property-pages.md)<br/>
オーバーライドするメソッドなど、プロパティページを実装する手順を示します。 ATLPages サンプルプログラムに基づく完全な例について説明します。

## <a name="related-sections"></a>関連項目

[ATLPages の例](../overview/visual-cpp-samples.md)<br/>
を使用してプロパティページを実装する ATLPages サンプルの抽象サンプル `IPropertyPageImpl` です。

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Active Template Library を使用してプログラミングする方法に関する概念説明のトピックへのリンクを提供します。

## <a name="see-also"></a>関連項目

[概念](../atl/active-template-library-atl-concepts.md)
