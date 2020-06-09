---
title: オートメーション
ms.date: 11/04/2016
helpviewer_keywords:
- Automation servers, about Automation servers
- clients, Automation
- programmatic control [MFC]
- properties [MFC], Automation
- MFC, COM support
- OLE Automation
- Automation
- servers [MFC], Automation
- Automation clients
- sample applications [MFC], Automation
- methods [MFC]
- passing parameters, Automation
- Automation method [MFC]
- Automation, passing parameters
- Automation property [MFC]
- MFC COM, Automation
- methods [MFC], Automation
ms.assetid: 329117f0-c1aa-4680-a901-bfb71277dfba
ms.openlocfilehash: e5790be14f26f59c2b51b339c8bee7c5eca7d692
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616521"
---
# <a name="automation"></a>オートメーション

オートメーション (以前の OLE オートメーション) を使うと、アプリケーションから、他のアプリケーションに実装されているオブジェクトを操作したり、他のアプリケーションから操作できるように自分のオブジェクトを公開したりできます。

[オートメーション サーバー](automation-servers.md) は、COM インターフェイスを通して他のアプリケーション ( [オートメーション クライアント](automation-clients.md)) に機能を公開するアプリケーション (一種の COM サーバー) です。 オートメーション クライアントは、この公開を通してオブジェクトに直接アクセスし、オブジェクトが提供するサービスを使用することで、特定の機能を自動化できます。

オートメーション サーバーとオートメーション クライアントは、COM インターフェイスを使用します。COM インターフェイスは、常に `IDispatch` から派生し、オートメーション型と呼ばれる一連のデータ型を受け取ったり返したりします。 他のアプリケーションからアクセス可能なメソッドやプロパティを提供し、オートメーション インターフェイスを公開するオブジェクトはすべて自動化できます。 OLE オブジェクトと COM オブジェクトは、どちらもオートメーションを利用できます。 オブジェクトの自動化は、ローカルでもリモートでも可能です。リモートとは、ネットワークでアクセス可能な別のコンピューターにあるという意味です。つまり、オートメーションには次の 2 つのカテゴリがあります。

- オートメーション (ローカル)。

- リモート オートメーション (分散 COM (DCOM) を使用したネットワーク経由)。

アプリケーションが他のアプリケーションでも役に立つ機能を備えている場合は、オブジェクトを公開することは有益です。 たとえば、ActiveX コントロールは一種のオートメーション サーバーで、ActiveX コントロールをホストするアプリケーションは ActiveX コントロールのオートメーション クライアントです。

ワード プロセッサから他のプログラムに公開されているスペル チェック機能も、オブジェクト公開の例です。 オブジェクトを公開すると、他のアプリケーションの既製の機能を利用できるようになるので、そのアプリケーションの機能が向上します。 このように、オートメーションは、再利用性やカプセル化などのオブジェクト指向プログラミングの原理をアプリケーション自体のレベルで利用しています。

さらに重要なのは、オートメーションがユーザーやソリューション プロバイダーに提供するサポートです。 標準的な仕様のインターフェイスを介してアプリケーションの機能を公開すると、さまざまなアプリケーション固有のマクロ言語ではなく、Microsoft Visual Basic などの単一の汎用プログラミング言語で広範なソリューションを構築できます。

Microsoft Excel、Microsoft Visual C++ など、多くの商用アプリケーションでは、その機能の大部分を自動化できます。 たとえば、Visual C++ では、 VBScript のマクロを記述することで、ビルド、コード編集、デバッグ作業などを自動化できます。

## <a name="passing-parameters-in-automation"></a><a name="_core_passing_parameters_in_automation"></a> オートメーションにおけるパラメーターの受け渡し

オートメーション メソッドの作成で問題になるのは、オートメーション サーバーとオートメーション クライアント間でデータを "安全" に受け渡すための統一したメカニズムを提供することです。 オートメーションは、 **VARIANT** 型を使ってデータを渡します。 **VARIANT** 型はタグ付きの共用体であり、 値を示すデータ メンバー (C++ の匿名共用体) と、この共用体に格納されている情報の型を示すデータ メンバーを持ちます。 **VARIANT** 型は、標準データ型の数、つまり 2 および 4 バイトの整数、4 および 8 バイトの浮動小数点数、文字列、およびブール値をサポートしています。 さらに、 **HRESULT** (OLE エラーコード)、**通貨**(固定小数点数値型)、 **date** (絶対日付と時刻) 型、およびインターフェイスへのポインターもサポートしてい `IUnknown` `IDispatch` ます。

**VARIANT** 型は、 [COleVariant](reference/colevariant-class.md) クラスにカプセル化されています。 サポートしている **CURRENCY** クラスと **DATE** クラスは、 [COleCurrency](reference/colecurrency-class.md) クラスと [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) クラスにカプセル化されています。

## <a name="automation-samples"></a>オートメーションのサンプル

- [AUTOCLIK](../overview/visual-cpp-samples.md) オートメーションの手法とリモート オートメーションの基礎を学習します。

- [ACDUAL](../overview/visual-cpp-samples.md) オートメーション サーバー アプリケーションにデュアル インターフェイスを追加します。

- [CALCDRIV](../overview/visual-cpp-samples.md) MFCCALC を起動するオートメーション クライアント アプリケーションです。

- [INPROC](../overview/visual-cpp-samples.md) インプロセス オートメーション サーバー アプリケーションの例を示します。

- [IPDRIVE](../overview/visual-cpp-samples.md) INPROC を起動するオートメーション クライアント アプリケーションです。

- [MFCCALC](../overview/visual-cpp-samples.md) オートメーション クライアント アプリケーションの例を示します。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [オートメーションクライアント](automation-clients.md)

- [オートメーション サーバー](automation-servers.md)

- [OLE●ole○](ole-in-mfc.md)

- [Active テクノロジ](mfc-com.md)

## <a name="what-do-you-want-to-do"></a>どうしたいんですか

- [オートメーション クラスを追加する](automation-servers.md)

- [タイプ ライブラリを使用する](automation-clients-using-type-libraries.md)

- [オートメーション サーバーにアクセスする](automation-servers.md)

- [C++ でオートメーション クライアントを記述する](automation-clients.md)

## <a name="see-also"></a>関連項目

[MFC COM](mfc-com.md)
