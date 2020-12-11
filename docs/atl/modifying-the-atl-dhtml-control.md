---
description: '詳細情報: ATL DHTML コントロールの変更'
title: ATL DHTML コントロールの変更
ms.date: 11/04/2016
helpviewer_keywords:
- HTML controls, modifying
- DHTML controls
- DHTML controls, modifying
ms.assetid: c053f35f-8629-4600-9595-721f5956777a
ms.openlocfilehash: 7ae9c102addd7a33341a8f16105a3581de10481e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159454"
---
# <a name="modifying-the-atl-dhtml-control"></a>ATL DHTML コントロールの変更

ATL コントロールウィザードには、コントロールをビルドして実行できるようにするためのスタートコードが用意されています。これにより、メソッドがどのようにプロジェクトファイルに記述されているか、および DHTML がディスパッチメソッドを使用してコントロールの C++ コードを呼び出す方法を確認できます。 任意のディスパッチメソッドをインターフェイスに追加できます。 次に、HTML リソース内のメソッドを呼び出すことができます。

## <a name="to-modify-the-atl-dhtml-control"></a>ATL DHTML コントロールを変更するには

1. **クラスビュー** で、コントロールプロジェクトを展開します。

   "UI" で終わるインターフェイスには、という1つのメソッドがあり `OnClick` ます。 "UI" で終了しないインターフェイスにはメソッドがありません。

1. `MethodInvoked`"UI" で終了しないインターフェイスに、というメソッドを追加します。

   このメソッドは、コントロールとの対話に DHTML で使用されるインターフェイスではなく、コンテナーとの対話のためにコントロールコンテナーで使用されるインターフェイスに追加されます。 このメソッドを呼び出すことができるのは、コンテナーだけです。

1. .Cpp ファイルでスタブメソッドを見つけ、メッセージボックスを表示するコードを追加します。次に例を示します。

   [!code-cpp[NVC_ATL_COM#5](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_1.cpp)]

1. という別のメソッドを追加し、今度は `HelloHTML` "UI" で終わるインターフェイスに追加します。 `HelloHTML`.Cpp ファイルでスタブメソッドを見つけ、メッセージボックスを表示するコードを追加します。次に例を示します。

   [!code-cpp[NVC_ATL_COM#6](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_2.cpp)]

1. `GoToURL`"UI" で終了しないインターフェイスに、3番目のメソッドを追加します。 次のように [IWebBrowser2:: Navigate](/previous-versions//aa752133\(v=vs.85\))を呼び出して、このメソッドを実装します。

   [!code-cpp[NVC_ATL_COM#7](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_3.cpp)]

   メソッドを使用できます。これは、ATL によって、 `IWebBrowser2` .h ファイル内のそのインターフェイスへのポインターが提供されるためです。

次に、作成したメソッドを呼び出すように HTML リソースを変更します。 これらのメソッドを呼び出すには、3つのボタンを追加します。

## <a name="to-modify-the-html-resource"></a>HTML リソースを変更するには

1. **ソリューションエクスプローラー** で、.htm ファイルをダブルクリックして HTML リソースを表示します。

   HTML、特に外部の Windows ディスパッチメソッドの呼び出しを確認します。 HTML はプロジェクトの `OnClick` メソッドを呼び出し、パラメーターはコントロールの本体 ( `theBody` ) と割り当てる色 (" `red` ") を示します。 メソッド呼び出しの後に続くテキストは、ボタンに表示されるラベルです。

1. 別の `OnClick` メソッドを追加し、色だけを変更します。 次に例を示します。

    ```html
    <br>
    <br>
    <BUTTON onclick='window.external.OnClick(theBody, "white");'>Refresh</BUTTON>
    ```

   このメソッドは、[ **更新**] というラベルのボタンを作成します。このボタンをクリックすると、コントロールを元の白の背景に戻すことができます。

1. 作成したメソッドに呼び出しを追加 `HelloHTML` します。 次に例を示します。

    ```html
    <br>
    <br>
    <BUTTON onclick='window.external.HelloHTML();'>HelloHTML</BUTTON>
    ```

   このメソッドは、ユーザーがクリックしてメッセージボックスを表示できる、 **HelloHTML** というラベルが付いたボタンを作成し `HelloHTML` ます。

変更した [DHTML コントロール](../atl/testing-the-modified-atl-dhtml-control.md)をビルドしてテストできるようになりました。

## <a name="see-also"></a>関連項目

[DHTML コントロールのサポート](../atl/atl-support-for-dhtml-controls.md)
