---
description: '詳細情報: オブジェクトへの接続ポイントの追加'
title: オブジェクトへの接続ポイントの追加
ms.date: 11/04/2016
helpviewer_keywords:
- connection points [C++], adding to ATL objects
- Implement Connection Point ATL wizard
ms.assetid: 843531be-4a36-4db0-9d54-e029b1a72a8b
ms.openlocfilehash: 7d8274ab37cef28a58666852aad24db7d945d26e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166240"
---
# <a name="adding-connection-points-to-an-object"></a>オブジェクトへの接続ポイントの追加

[ATL チュートリアル](../atl/active-template-library-atl-tutorial.md)では、接続ポイントをサポートするコントロールを作成する方法、イベントを追加する方法、コネクションポイントを実装する方法について説明します。 ATL では、 [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) クラスを使用して接続ポイントを実装します。

コネクションポイントを実装するには、次の2つの選択肢があります。

- コントロールまたはオブジェクトに接続ポイントを追加して、独自の送信イベントソースを実装します。

- 別のタイプライブラリで定義されている接続ポイントインターフェイスを再利用します。

どちらの場合も、接続ポイントの実装ウィザードはタイプライブラリを使用して作業を行います。

### <a name="to-add-a-connection-point-to-a-control-or-object"></a>コントロールまたはオブジェクトに接続ポイントを追加するには

1. .Idl ファイルのライブラリブロックにディスパッチインターフェイスを定義します。 ATL コントロールウィザードを使用してコントロールを作成したときに、接続ポイントのサポートを有効にした場合、ディスパッチインターフェイスは既に作成されています。 コントロールを作成したときに接続ポイントのサポートを有効にしなかった場合は、.idl ファイルにディスパッチインターフェイスを手動で追加する必要があります。 ディスパッチインターフェイスの例を次に示します。 送信インターフェイスはディスパッチインターフェイスである必要はありませんが、VBScript や JScript などの多くのスクリプト言語ではこれが必要であるため、この例では2つのディスパッチインターフェイスを使用します。

   [!code-cpp[NVC_ATL_Windowing#81](../atl/codesnippet/cpp/adding-connection-points-to-an-object_1.idl)]

   uuidgen.exe または guidgen.exe ユーティリティを使用して GUID を生成します。

2. `[default,source]`プロジェクトの .idl ファイル内のオブジェクトのコクラスにインターフェイスとしてディスパッチインターフェイスを追加します。 ここでも、コントロールの作成時に接続ポイントのサポートを有効にした場合、ATL コントロールウィザードによってエントリが作成され `[default,source` ます。 このエントリを手動で追加するには、次のように太字で行を追加します。

   [!code-cpp[NVC_ATL_Windowing#82](../atl/codesnippet/cpp/adding-connection-points-to-an-object_2.idl)]

   例については、 [Circ](../overview/visual-cpp-samples.md) ATL サンプルの .idl ファイルを参照してください。

3. メソッドとプロパティをイベントインターフェイスに追加するには、クラスビューを使用します。 クラスビューでクラスを右クリックし、ショートカットメニューの [ **追加** ] をポイントして、[ **接続ポイントの追加**] をクリックします。

4. 接続ポイントの実装ウィザードの [ **ソースインターフェイス** ] ボックスの一覧で、[ **プロジェクトのインターフェイス**] を選択します。 コントロールのインターフェイスを選択して **[OK]** を押すと、次のようになります。

   - イベントの発信呼び出しを行うコードを実装するイベントプロキシクラスを使用して、ヘッダーファイルを生成します。

   - コネクションポイントマップにエントリを追加します。

   また、コンピューター上のすべてのタイプライブラリの一覧も表示されます。 別のタイプライブラリにあるものとまったく同じ出力インターフェイスを実装する場合は、これらの他のタイプライブラリのいずれかを使用して接続ポイントを定義する必要があります。

### <a name="to-reuse-a-connection-point-interface-defined-in-another-type-library"></a>別のタイプライブラリで定義されている接続ポイントインターフェイスを再利用するには

1. クラスビューで、 **BEGIN_COM_MAP** マクロを実装するクラスを右クリックし、ショートカットメニューの [ **追加** ] をポイントして、[ **接続ポイントの追加**] をクリックします。

2. 接続ポイントの実装ウィザードで、タイプライブラリとタイプライブラリ内のインターフェイスを選択し、[ **追加**] をクリックします。

3. 次のいずれかの方法で .idl ファイルを編集します。

   - イベントソースが使用されているオブジェクトの .idl ファイルからディスパッチインターフェイスをコピーします。

   - そのタイプライブラリで **importlib** 命令を使用します。

## <a name="see-also"></a>関連項目

[接続ポイント](../atl/atl-connection-points.md)
