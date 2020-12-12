---
description: 詳細については、「DHTML からの C++ コードの呼び出し」を参照してください。
title: 呼び出し (DHTML から C++ コードを)
ms.date: 11/04/2016
helpviewer_keywords:
- DHTML, calling C++ code from
ms.assetid: 37329acd-4c22-40ca-a85a-b7480748f75f
ms.openlocfilehash: d880b0e9cb2f0b9d5228df7da4fc96fceeb87943
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148487"
---
# <a name="calling-c-code-from-dhtml"></a>呼び出し (DHTML から C++ コードを)

DHTML コントロールは、テストコンテナーや Internet Explorer などのコンテナーでホストできます。 テストコンテナーにアクセスする方法の詳細については [、「テストコンテナーでのプロパティとイベントのテスト](../mfc/testing-properties-and-events-with-test-container.md) 」を参照してください。

コントロールをホストしているコンテナーは、通常のコントロールインターフェイスを使用してコントロールと通信します。 DHTML は、"UI" で終わるディスパッチインターフェイスを使用して、C++ コードと HTML リソースと通信します。 [ATL DHTML コントロールを変更](../atl/modifying-the-atl-dhtml-control.md)する場合は、これらの異なるインターフェイスによって呼び出されるメソッドを追加することをお勧めします。

DHTML から C++ コードを呼び出す例を確認するには、ATL コントロールウィザードを使用して [dhtml コントロールを作成](../atl/creating-an-atl-dhtml-control.md) し、ヘッダーファイルと HTML ファイル内のコードを確認します。

## <a name="declaring-webbrowser-methods-in-the-header-file"></a>ヘッダーファイルでの WebBrowser メソッドの宣言

DHTML UI から C++ メソッドを呼び出すには、コントロールの UI インターフェイスにメソッドを追加する必要があります。 たとえば、ATL コントロールウィザードによって作成されたヘッダーファイルには、ウィザードで生成された `OnClick` コントロールの UI インターフェイスのメンバーである C++ メソッドが含まれています。

`OnClick`コントロールの .h ファイルを調べます。

[!code-cpp[NVC_ATL_COM#4](../atl/codesnippet/cpp/calling-cpp-code-from-dhtml_1.h)]

最初のパラメーターである *Pdispbody* は、body オブジェクトのディスパッチインターフェイスへのポインターです。 2番目のパラメーター *Varcolor* は、コントロールに適用する色を示します。

## <a name="calling-c-code-in-the-html-file"></a>HTML ファイルでの C++ コードの呼び出し

ヘッダーファイルで WebBrowser メソッドを宣言したら、HTML ファイルからメソッドを呼び出すことができます。 HTML ファイルで、ATL コントロールウィザードによって、3つの Windows ディスパッチメソッドが挿入されていることに注意してください。 `OnClick` コントロールの背景色を変更するためにメッセージをディスパッチする3つのメソッドです。

HTML ファイル内のいずれかのメソッドを確認します。

`<BUTTON onclick='window.external.OnClick(theBody, "red");'>Red</BUTTON>`

上記の HTML コードでは、ウィンドウの外部メソッドは、 `OnClick` ボタンタグの一部として呼び出されます。 メソッドには、2つのパラメーター ( `theBody` HTML ドキュメントの本文を参照する) と `"red"` 、ボタンがクリックされたときにコントロールの背景色が赤に変更されることを示すという2つのパラメーターがあります。 次のタグは、 `Red` ボタンのラベルです。

独自のメソッドの提供の詳細については [、「ATL DHTML コントロールの変更](../atl/modifying-the-atl-dhtml-control.md) 」を参照してください。 HTML ファイルの詳細については、「 [DHTML コントロールプロジェクトの要素の識別](../atl/identifying-the-elements-of-the-dhtml-control-project.md) 」を参照してください。

## <a name="see-also"></a>関連項目

[DHTML コントロールのサポート](../atl/atl-support-for-dhtml-controls.md)
