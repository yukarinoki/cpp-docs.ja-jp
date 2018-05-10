---
title: OLE DB 準拠合致テストを渡す |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- conformance testing
- conformance testing [OLE DB]
- OLE DB providers, testing
ms.assetid: d1a4f147-2edd-476c-b452-0e6a0ac09891
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 11677e6295956de768c7ebc0c113d775b066bb0c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="passing-ole-db-conformance-tests"></a>OLE DB 準拠合致テスト
プロバイダーを一貫したものにするには、Data Access SDK は、OLE DB 準拠合致テストのセットを提供します。 テストは、プロバイダーのすべての側面を確認し、妥当なという保証は正常に、プロバイダーの機能を提供します。 Microsoft Data Access SDK では、OLE DB 準拠合致テストを検索できます。 このセクションでは、準拠テストに合格する必要があることについて説明します。 OLE DB 準拠合致テストの実行方法の詳細については、SDK を参照してください。  
  
## <a name="running-the-conformance-tests"></a>準拠合致テストを実行しています。  
 Visual C 6.0 では、OLE DB プロバイダー テンプレートは、多数の値とプロパティを確認するためのフック関数を追加します。 これらの関数のほとんどは、準拠合致テストへの応答に追加されました。  
  
> [!NOTE]
>  OLE DB 準拠のテストに合格するプロバイダーのいくつかの検証機能を追加する必要があります。  
  
 このプロバイダーでは、2 つの検証ルーチンが必要です。 最初のルーチン`CRowsetImpl::ValidateCommandID`、行セット クラスの一部です。 プロバイダー テンプレートによって、行セットの作成時に呼び出されます。 このサンプルでは、このルーチンを使用してインデックスをサポートしないコンシューマーに通知します。 最初の呼び出しが`CRowsetImpl::ValidateCommandID`(注プロバイダーが使用する、 **_RowsetBaseClass**に対するインターフェイス マップに追加された typedef`CMyProviderRowset`で[プロバイダーのブックマーク サポート](../../data/oledb/provider-support-for-bookmarks.md)する必要はありませんので、テンプレートの引数の長い行を入力)。 次に、返す**DB_E_NOINDEX**インデックス パラメーターがない場合**NULL** (コンシューマーが私たちのインデックスを使用することを示します)。 コマンド Id の詳細については、OLE DB 仕様を参照して、探して**iopenrowset::openrowset**です。  
  
 次のコードは、 **ValidateCommandID**検証ルーチン。  
  
```cpp
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
// Class: CMyProviderRowset   
  
HRESULT ValidateCommandID(DBID* pTableID, DBID* pIndexID)  
{  
   HRESULT hr = _RowsetBaseClass::ValidateCommandID(pTableID, pIndexID);  
   if (hr != S_OK)  
      return hr;  
  
   if (pIndexID != NULL)  
      return DB_E_NOINDEX;    // Doesn't support indexes  
  
   return S_OK;  
}  
```  
  
 プロバイダー テンプレートの呼び出し、`OnPropertyChanged`メソッド、プロパティの誰かが変更されるたびに、 **DBPROPSET_ROWSET**グループ。 適切なオブジェクトに追加の他のグループのプロパティを処理する場合 (つまり、 **DBPROPSET_SESSION**移動するチェック、`CMyProviderSession`クラス)。  
  
 コードは、まず別、プロパティがリンクされているかどうかを確認します。 プロパティをチェーンされている場合は設定、 **DBPROP_BOOKMARKS**プロパティを True にします。 OLE DB 仕様の「付録 C には、プロパティに関する情報が含まれていますいます。 この情報も示しますプロパティがもう 1 つにチェーンされているかどうか。  
  
 追加する場合がありますも、`IsValidValue`ルーチンをコードにします。 テンプレートの呼び出し`IsValidValue`プロパティを設定しようとしています。 プロパティの値を設定するときに、追加の処理を必要とする場合は、このメソッドをオーバーライドします。 プロパティ セットごとにこれらのメソッドのいずれかのことができます。  
  
## <a name="threading-issues"></a>スレッド処理の問題  
 既定では、OLE DB プロバイダー ウィザード ATL OLE DB プロバイダー ウィザードでは、アパートメント モデルで実行するプロバイダーのコードを生成します。 準拠合致テストでこのコードを実行しようとすると、最初にエラーが表示されます。 これは、空き Ltm.exe、OLE DB 準拠合致テストを実行するためのツールの既定値は、スレッドします。 OLE DB プロバイダー ウィザード コードは、アパートメント モデルのパフォーマンスと使いやすさを既定値です。  
  
 この問題を解決するには、LTM を変更するか、プロバイダーを変更します。  
  
#### <a name="to-change-ltm-to-run-in-apartment-threaded-mode"></a>モードをスレッド アパートメントで実行する LTM を変更するには  
  
1.  LTM メイン メニューで、をクリックして**ツール**、クリックして**オプション**です。  
  
2.  **全般**からスレッド モデルの変更 タブで、**空きスレッド**に**Apartment Threaded**です。  
  
 プロバイダーを変更する、空きスレッド モードで実行します。  
  
-   プロバイダーのプロジェクトでのすべてのインスタンスを検索`CComSingleThreadModel`置き換えます`CComMultiThreadModel`、データ ソース、セッション、および行セットのヘッダーに必要があります。  
  
-   .Rgs ファイルで、変更、スレッディング モデルから**アパートメント**に**両方**です。  
  
-   フリー スレッドのプログラミング (つまり、書き込み時のロック) の規則に従って適切なプログラミングします。  
  
## <a name="see-also"></a>関連項目  
 [高度なプロバイダー手法](../../data/oledb/advanced-provider-techniques.md)