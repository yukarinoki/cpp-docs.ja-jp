---
title: 読み取り専用プロバイダーのテスト
ms.date: 11/04/2016
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, calling
- OLE DB providers, testing
ms.assetid: e4aa30c1-391b-41f8-ac73-5270e46fd712
ms.openlocfilehash: dc3c4ea36aa9dac64f2aa7861fd5d51927c77ecd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209503"
---
# <a name="testing-the-read-only-provider"></a>読み取り専用プロバイダーのテスト

プロバイダーをテストするには、コンシューマーが必要です。 コンシューマーがプロバイダーと一致するかどうかを決定するのに役立ちます。 OLE DB コンシューマーテンプレートは、OLE DB のシンラッパーで、プロバイダー COM オブジェクトと一致します。 ソースはコンシューマーテンプレートに付属しているため、プロバイダーを使用して簡単にデバッグできます。 コンシューマーテンプレートは、非常に小さな高速な方法でコンシューマーアプリケーションを開発することもできます。

このトピックの例では、テストコンシューマー用の既定の MFC アプリケーションウィザードアプリケーションを作成します。 テストアプリケーションは OLE DB コンシューマーテンプレートコードが追加された単純なダイアログです。

## <a name="to-create-the-test-application"></a>テスト アプリケーションを作成するには

1. **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。

1. **[プロジェクトの種類]** ペインで、[**インストールされている** > **Visual C++**  > **MFC/ATL** ] フォルダーを選択します。 **[テンプレート]** ペインで、 **[MFC アプリケーション]** を選択します。

1. プロジェクト名として「 *TestProv*」と入力し、[ **OK]** をクリックします。

   **MFC アプリケーション**ウィザードが表示されます。

1. **[アプリケーションの種類]** ページで、[**ダイアログベース]** を選択します。

1. **[高度な機能]** ページで、 **[Automation]** を選択し、 **[完了]** をクリックします。

> [!NOTE]
> `CTestProvApp::InitInstance`に `CoInitialize` を追加した場合、アプリケーションはオートメーションサポートを必要としません。

**[TestProv]** ダイアログボックス (IDD_TESTPROV_DIALOG) を表示および編集するには**リソースビュー**でそれを選択します。 ダイアログボックスで、行セット内の文字列ごとに1つずつ、2つのリストボックスを配置します。 両方のリストボックスの並べ替えプロパティを無効にするには、 **Alt**キーを押し+リストボックスが選択されているときに**enter**キーを押し、 **sort**プロパティを**False**に設定します。 また、ダイアログボックスに **[実行]** ボタンを配置して、ファイルをフェッチします。 完了した **[TestProv]** ダイアログボックスには、それぞれ "string 1" と "string 2" というラベルが付いた2つのリストボックスがあります。また、 **[OK]** 、 **[キャンセル**]、および **[実行]** ボタンもあります。

ダイアログクラス (この場合は TestProvDlg) のヘッダーファイルを開きます。 (クラス宣言の外側で) 次のコードをヘッダーファイルに追加します。

```cpp
////////////////////////////////////////////////////////////////////////
// TestProvDlg.h
#include <atldbcli.h>  

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

このコードは、行セット内の列を定義するユーザーレコードを表します。 クライアントは `IAccessor::CreateAccessor`を呼び出すと、これらのエントリを使用して、バインドする列を指定します。 OLE DB コンシューマーテンプレートでは、列を動的にバインドすることもできます。 COLUMN_ENTRY マクロは、PROVIDER_COLUMN_ENTRY マクロのクライアント側バージョンです。 2つの COLUMN_ENTRY マクロは、2つの文字列の序数、型、長さ、およびデータメンバーを指定します。

**Ctrl**キーを押しながら **[実行]** ボタンをダブルクリックして、 **[実行]** ボタンのハンドラー関数を追加します。 関数に次のコードを配置します。

```cpp
///////////////////////////////////////////////////////////////////////
// TestProvDlg.cpp

void CTestProvDlg::OnRun()
{
   CCommand<CAccessor<CProvider>> table;
   CDataSource source;
   CSession session;

   if (source.Open("Custom.Custom.1", NULL) != S_OK)
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

`CCommand`、`CDataSource`、および `CSession` クラスはすべて OLE DB コンシューマーテンプレートに属しています。 各クラスは、プロバイダー内の COM オブジェクトを模倣しています。 `CCommand` オブジェクトは、ヘッダーファイルで宣言されている `CProvider` クラスをテンプレートパラメーターとして受け取ります。 `CProvider` パラメーターは、プロバイダーからのデータにアクセスするために使用するバインディングを表します。

各クラスを開く行によって、プロバイダーに各 COM オブジェクトが作成されます。 プロバイダーを検索するには、プロバイダーの `ProgID` を使用します。 システムレジストリから `ProgID` を取得することも、カスタムの .rgs ファイルを検索することもできます (プロバイダーのディレクトリを開き、`ProgID` キーを検索します)。

`MyProv` サンプルには、MyData ファイルが含まれています。 独自のファイルを作成するには、エディターを使用して、文字列の間に**enter**キーを押して、偶数の文字列を入力します。 ファイルを移動する場合は、パス名を変更します。

`table.Open` 行に文字列 "c:\\\ samples\\\myprov\\\MyData.txt" を渡します。 `Open` の呼び出しにステップインすると、この文字列がプロバイダーの `SetCommandText` メソッドに渡されることがわかります。 `ICommandText::Execute` メソッドでその文字列が使用されていることに注意してください。

データをフェッチするには、テーブルで `MoveNext` を呼び出します。 `MoveNext` は、`IRowset::GetNextRows`、`GetRowCount`、および `GetData` の各関数を呼び出します。 行がなくなった場合 (つまり、行セットの現在位置が `GetRowCount`を超えている場合)、ループは終了します。

行がなくなった場合、プロバイダーは DB_S_ENDOFROWSET を返します。 DB_S_ENDOFROWSET 値がエラーではありません。 データフェッチループをキャンセルし、SUCCEEDED マクロを使用しないようにするには、常に S_OK をチェックする必要があります。

これで、プログラムをビルドしてテストできるようになります。

## <a name="see-also"></a>参照

[単純な読み取り専用プロバイダーの機能の拡張](../../data/oledb/enhancing-the-simple-read-only-provider.md)
