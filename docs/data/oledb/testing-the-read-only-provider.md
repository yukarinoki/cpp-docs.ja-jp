---
title: 読み取り専用プロバイダーのテスト |Microsoft ドキュメント
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
- OLE DB providers, calling
- OLE DB providers, testing
ms.assetid: e4aa30c1-391b-41f8-ac73-5270e46fd712
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 703d33f44fae534b206050e85086edb1ccc816f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="testing-the-read-only-provider"></a>読み取り専用プロバイダーのテスト
プロバイダーをテストするには、コンシューマーが必要です。 コンシューマーはプロバイダーと一致させる場合に役立ちます。 OLE DB コンシューマー テンプレートは、OLE DB の thin ラッパーでプロバイダーの COM オブジェクトと一致します。 これらのプロバイダーのデバッグが容易には、ソースは、コンシューマー テンプレートに含まれる、ためです。 コンシューマー テンプレートは、コンシューマー アプリケーションを開発する非常に小さく、高速の方法ではもです。  
  
 このトピックの例では、テストのコンシューマーの既定の MFC アプリケーション ウィザード アプリケーションを作成します。 テスト アプリケーションは、OLE DB コンシューマー テンプレート コードが追加された単純なダイアログです。  
  
### <a name="to-create-the-test-application"></a>テスト アプリケーションを作成するには  
  
1.  **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。  
  
2.  プロジェクトの種類 ウィンドウで、選択、 **Visual C プロジェクト**フォルダーです。 [テンプレート] ペインで選択**MFC アプリケーション**です。  
  
3.  プロジェクト名を入力してください。 **TestProv**、をクリックし、 **OK**です。  
  
     MFC アプリケーション ウィザードが表示されます。  
  
4.  **アプリケーションの種類**] ページで、[**ダイアログ ベース**です。  
  
5.  **高度な機能**] ページで、[**オートメーション**をクリックし、**完了**です。  
  
> [!NOTE]
>  追加する場合に、アプリケーションでオートメーションのサポートが必要ありません**CoInitialize**で**CTestProvApp::InitInstance**です。  
  
 表示して、リソース ビューで選択して、TestProv ダイアログ ボックス (IDD_TESTPROV_DIALOG) を編集します。 ダイアログ ボックスで、行セット内の各文字列の 1 つ、2 つのリスト ボックスを配置します。 ボックスをクリックするとのリスト ボックスを選択すると、alt キーを押しながら Enter を押してリストを並び替えプロパティ無効にする、**スタイル**タブをクリックし、オフにすると、**並べ替え**チェック ボックスをオンします。 また、配置、**実行**ファイルをフェッチするダイアログ ボックスにボタンをクリックします。 終了 TestProv ダイアログ ボックスが「文字列 1」と「2 を文字列」をそれぞれ; という 2 つのリスト ボックスがある必要があります。さらに、 **OK**、**キャンセル**と**実行**ボタン。  
  
 (このケース TestProvDlg.h) でダイアログ クラスのヘッダー ファイルを開きます。 ヘッダー ファイル (、クラス宣言の外部に次のコードを追加します。  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// TestProvDlg.h  
  
class CProvider   
{  
// Attributes  
public:  
   char   szField1[16];  
   char   szField2[16];  
  
   // Binding Maps  
BEGIN_COLUMN_MAP(CProvider)  
   COLUMN_ENTRY(1, szField1)  
   COLUMN_ENTRY(2, szField2)  
END_COLUMN_MAP()  
};  
```  
  
 コードでは、列は、行セットになりますを定義するユーザー レコードを表します。 クライアントが呼び出すと**iaccessor::createaccessor**、これらのエントリを使用してバインドする列を指定します。 OLE DB コンシューマー テンプレートを使用して、列を動的にバインドすることもできます。 COLUMN_ENTRY マクロは、PROVIDER_COLUMN_ENTRY マクロのクライアント側のバージョンです。 2 つの COLUMN_ENTRY マクロは、序数、2 つの文字列の型、長さ、およびデータ メンバーを指定します。  
  
 ハンドラー関数を追加、**実行**ボタンをクリックして、CTRL キーを押しをダブルクリックして、**実行**ボタンをクリックします。 関数では、次のコードを配置します。  
  
```cpp
///////////////////////////////////////////////////////////////////////  
// TestProvDlg.cpp  
  
void CtestProvDlg::OnRun()  
{  
   CCommand<CAccessor<CProvider>> table;  
   CDataSource source;  
   CSession   session;  
  
   if (source.Open("MyProvider.MyProvider.1", NULL) != S_OK)  
      return;  
  
   if (session.Open(source) != S_OK)  
      return;  
  
   if (table.Open(session, _T("c:\\samples\\myprov\\myData.txt")) != S_OK)  
      return;  
  
   while (table.MoveNext() == S_OK)  
   {  
      m_ctlString1.AddString(table.szField1);  
      m_ctlString2.AddString(table.szField2);  
   }  
}  
```  
  
 `CCommand`、 `CDataSource`、および`CSession`OLE DB コンシューマー テンプレートに属しているすべてのクラスです。 各クラスは、プロバイダーでの COM オブジェクトを模倣します。 `CCommand`オブジェクトは、`CProvider`テンプレート パラメーターとして、ヘッダー ファイルで宣言したクラスです。 `CProvider`パラメーターは、プロバイダーからデータにアクセスするために使用するバインディングを表します。 ここでは、`Open`データ ソース、セッション、およびコマンドのコード。  
  
```  
if (source.Open("MyProvider.MyProvider.1", NULL) != S_OK)  
   return;  
  
if (session.Open(source) != S_OK)  
   return;  
  
if (table.Open(session, _T("c:\\samples\\myprov\\myData.txt")) != S_OK)  
   return;  
```  
  
 開くには、各クラスを行では、プロバイダーの各 COM オブジェクトを作成します。 プロバイダを探しするには、プロバイダーの ProgID を使用します。 ProgID を取得するには、システム レジストリからや MyProvider.rgs ファイル内の検索 (プロバイダーの ProgID のキーを検索してディレクトリを開きます)。  
  
 MyData.txt ファイルは MyProv サンプルに含まれます。 独自のファイルを作成するには、エディターを使用し、各文字列間で ENTER キーを押して、文字列の偶数を入力します。 ファイルを移動する場合は、パス名を変更します。  
  
 文字列で渡す"c:\\\samples\\\myprov\\\MyData.txt"で、`table.Open`行です。 ステップ インする場合、`Open`この文字列が渡されるを参照する、呼び出し、`SetCommandText`プロバイダーのメソッドです。 なお、`ICommandText::Execute`メソッドは、その文字列を使用します。  
  
 データをフェッチする呼び出し`MoveNext`テーブルにします。 `MoveNext` 呼び出し、 **irowset::getnextrows**、 `GetRowCount`、および`GetData`関数。 これ以上の行がある場合 (つまり、行セット内の現在位置がより大きい`GetRowCount`)、ループが終了します。  
  
```  
while (table.MoveNext() == S_OK)  
{  
   m_ctlString1.AddString(table.szField1);  
   m_ctlString2.AddString(table.szField2);  
}  
```  
  
 これ以上の行がある場合にプロバイダーが返すことに注意してください**DB_S_ENDOFROWSET**です。 **DB_S_ENDOFROWSET**値がエラーではありません。 に対して常に確認する必要があります`S_OK`データのフェッチのループをキャンセルし、SUCCEEDED マクロを使用しません。  
  
 ビルドし、プログラムをテストできるようになりましたにします。  
  
## <a name="see-also"></a>関連項目  
 [単純な読み取り専用プロバイダーの機能の拡張](../../data/oledb/enhancing-the-simple-read-only-provider.md)