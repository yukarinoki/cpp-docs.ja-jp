---
title: オブジェクトへの接続ポイントの追加 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], adding to ATL objects
- Implement Connection Point ATL wizard
ms.assetid: 843531be-4a36-4db0-9d54-e029b1a72a8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71f9d136ccdeded02303894195c7b8126acafd9c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="adding-connection-points-to-an-object"></a>オブジェクトへの接続ポイントの追加
[ATL チュートリアル](../atl/active-template-library-atl-tutorial.md)コネクション ポイントのサポートでコントロールを作成する方法、イベントを追加する方法と、接続ポイントを実装する方法を示しています。 ATL 接続ポイントでは、 [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md)クラスです。  
  
 接続ポイントを実装するのには、2 つの選択肢があります。  
  
-   コントロールまたはオブジェクトへの接続ポイントを追加することで、独自の送信のイベント ソースを実装します。  
  
-   別のタイプ ライブラリで定義された接続ポイントのインターフェイスを再利用できます。  
  
 どちらの場合は、接続ポイントの実装ウィザードは、作業のために、タイプ ライブラリを使用します。  
  
### <a name="to-add-a-connection-point-to-a-control-or-object"></a>コントロールまたはオブジェクトへの接続ポイントを追加するには  
  
1.  .Idl ファイルのライブラリ ブロックにディスパッチ インターフェイスを定義します。 ATL コントロール ウィザードで、コントロールを作成するときに、接続ポイントのサポートが有効な場合、ディスパッチ インターフェイスは既に作成されています。 コントロールを作成するときの接続ポイントのサポートを有効にしなかった、.idl ファイルにディスパッチ インターフェイスを手動で追加する必要があります。 ディスパッチ インターフェイスの例を次に示します。 発信インターフェイスは必要ありませんディスパッチ インターフェイスであるため、この例は、次の 2 つのディスパッチ インターフェイスを使用してこれには、VBScript や JScript など多くのスクリプト言語必要があります。  
  
     [!code-cpp[NVC_ATL_Windowing#81](../atl/codesnippet/cpp/adding-connection-points-to-an-object_1.idl)]  
  
     Uuidgen.exe または guidgen.exe ユーティリティを使用して、GUID を生成します。  
  
2.  としてディスパッチ インターフェイスを追加、`[default,source]`プロジェクトの .idl ファイル内のオブジェクトのコクラスのインターフェイスです。 ここでも、コントロールを作成するときに、接続ポイントのサポートが有効な場合、ATL コントロール ウィザード、作成、 `[default,source`] エントリ。 このエントリを手動で追加するには、太字で、行を追加します。  
  
     [!code-cpp[NVC_ATL_Windowing#82](../atl/codesnippet/cpp/adding-connection-points-to-an-object_2.idl)]  
  
     .Idl ファイルを参照して、 [Circ](../visual-cpp-samples.md)例については、ATL のサンプルです。  
  
3.  イベント インターフェイスにメソッドとプロパティを追加するのにには、クラス ビューを使用します。 クラス ビュー内のクラス名を右クリックし、順にポイント**追加**クリックしてショートカット メニューの **接続ポイントの追加**です。  
  
4.  **ソース インターフェイス**実装接続ポイントのウィザード、[選択] のリスト ボックス**インターフェイス**です。 キーを押して、コントロールのインターフェイスを選択するかどうかは**OK**が表示されます。  
  
    -   イベントの呼び出しを送信すると、コードを実装するイベント プロキシ クラスのヘッダー ファイルを生成します。  
  
    -   コネクション ポイントのマップにエントリを追加します。  
  
     タイプ ライブラリのすべての一覧は、コンピューターにも表示されます。 これら他のタイプ ライブラリの 1 つは別のタイプ ライブラリで検出された正確な同じアウトゴーイング インターフェイスを実装する場合、接続ポイントを定義するのにのみ使用する必要があります。  
  
### <a name="to-reuse-a-connection-point-interface-defined-in-another-type-library"></a>コネクション ポイントのインターフェイスを再利用するのには、別のタイプ ライブラリで定義されています。  
  
1.  クラス ビューを実装するクラスを右クリックし、 **BEGIN_COM_MAP**マクロ、順にポイント**追加**クリックしてショートカット メニューの **接続ポイントの追加**です。  
  
2.  接続ポイントの実装ウィザードで、タイプ ライブラリ内のタイプ ライブラリとインターフェイスを選択し、をクリックして**追加**です。  
  
3.  .Idl ファイルを編集します。  
  
    -   イベント ソースが指定されているオブジェクトの .idl ファイルからディスパッチ インターフェイスをコピーします。  
  
    -   使用して、 **importlib**そのタイプ ライブラリに命令します。  
  
## <a name="see-also"></a>関連項目  
 [接続ポイント](../atl/atl-connection-points.md)

