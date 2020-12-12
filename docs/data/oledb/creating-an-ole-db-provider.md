---
description: 詳細については、OLE DB プロバイダーの作成に関するページを参照してください。
title: OLE DB プロバイダーの作成
ms.date: 10/13/2018
helpviewer_keywords:
- OLE DB providers, creating
- OLE DB provider templates, creating providers
ms.assetid: f73017c3-c89f-41a6-a306-ea992cf6092c
ms.openlocfilehash: 69dc9311a79f2739636633b2d268343a92d2dac9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287802"
---
# <a name="creating-an-ole-db-provider"></a>OLE DB プロバイダーの作成

OLE DB プロバイダーを作成するには、ウィザードを使用して ATL COM プロジェクトとプロバイダーを作成し、OLE DB テンプレートを使用してファイルを変更することをお勧めします。 プロバイダーをカスタマイズするときに、不要なプロパティをコメントアウトしたり、オプションのインターフェイスを追加したりすることができます。

基本的な手順は次のとおりです。

1. **Atl プロジェクトウィザード** を使用して、基本的なプロジェクトファイルと **atl oledb プロバイダーウィザード** を作成し、プロバイダーを作成します ([新しい項目の追加] の [**インストールされ** た Visual C++ atl フォルダーから **atl oledb プロバイダー** を選択し  >    >  ます)。 

   > [!NOTE]
   > **ATL OLEDB プロバイダー** を追加する前に、プロジェクトに MFC サポートが含まれている必要があります。

1. `Execute` [Ccustomrowset (customrs .h)](cmyproviderrowset-myproviderrs-h.md)でメソッドのコードを変更します。 例については、「 [OLE DB プロバイダーへの文字列の読み取り](../../data/oledb/reading-strings-into-the-ole-db-provider.md)」を参照してください。

1. [Customds .h](cmyprovidersource-myproviderds-h.md)、 [customds](cmyprovidersession-myprovidersess-h.md)、および[customds](cmyproviderrowset-myproviderrs-h.md)のプロパティマップを編集します。 ウィザードでは、プロバイダーが実装する可能性のあるすべてのプロパティを含むプロパティマップが作成されます。 プロパティマップを参照し、プロバイダーがサポートする必要のないプロパティを削除またはコメントアウトします。

1. [Ccustomrowset (CustomRS .h)](cmyproviderrowset-myproviderrs-h.md)にある PROVIDER_COLUMN_MAP を更新します。 例については、「 [OLE DB プロバイダーに文字列を格納](../../data/oledb/storing-strings-in-the-ole-db-provider.md)する」を参照してください。

1. プロバイダーをテストする準備ができたら、プロバイダーの列挙体でプロバイダーを検索してテストできます。 列挙体でプロバイダーを検索するテストコードの例については、 [CATDB](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/catdb) と [DBVIEWER](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer) のサンプル、または「 [単純なコンシューマーの実装](../../data/oledb/implementing-a-simple-consumer.md)」の例を参照してください。

1. 必要なインターフェイスを追加します。 例については、「 [Simple Read-Only Provider の拡張](../../data/oledb/enhancing-the-simple-read-only-provider.md)」を参照してください。

   > [!NOTE]
   > 既定では、ウィザードによって OLE DB レベル0に準拠したコードが生成されます。 アプリケーションがレベル0に準拠した状態を維持するには、ウィザードで生成されたインターフェイスをコードから削除しないでください。

## <a name="see-also"></a>関連項目

[CatDB サンプル: データソーススキーマブラウザー](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/catdb)<br/>
[DBViewer サンプル: データベースブラウザー](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/dbviewer)
