---
description: 詳細については、Read-Only プロバイダーのテストに関するページを参照してください。
title: 読み取り専用プロバイダーのテスト
ms.date: 11/04/2016
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, calling
- OLE DB providers, testing
ms.assetid: e4aa30c1-391b-41f8-ac73-5270e46fd712
ms.openlocfilehash: 2fbe0e7fb67b83cae65848939fa63bce42dab173
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272696"
---
# <a name="testing-the-read-only-provider"></a>読み取り専用プロバイダーのテスト

プロバイダーをテストするには、コンシューマーが必要です。 コンシューマーがプロバイダーと一致するかどうかを決定するのに役立ちます。 OLE DB コンシューマーテンプレートは、OLE DB のシンラッパーで、プロバイダー COM オブジェクトと一致します。 ソースはコンシューマーテンプレートに付属しているため、プロバイダーを使用して簡単にデバッグできます。 コンシューマーテンプレートは、非常に小さな高速な方法でコンシューマーアプリケーションを開発することもできます。

このトピックの例では、テストコンシューマー用の既定の MFC アプリケーションウィザードアプリケーションを作成します。 テストアプリケーションは OLE DB コンシューマーテンプレートコードが追加された単純なダイアログです。

## <a name="to-create-the-test-application"></a>テスト アプリケーションを作成するには

1. **[ファイル]** メニューの **[新規作成]** をクリックし、**[プロジェクト]** をクリックします。

1. [**プロジェクトの種類**] ペインで、[**インストールされている**  >  **Visual C++**  >  **MFC/ATL** ] フォルダーを選択します。 [ **テンプレート** ] ペインで、[ **MFC アプリケーション**] を選択します。

1. プロジェクト名として「 *TestProv*」と入力し、[ **OK]** をクリックします。

   **MFC アプリケーション** ウィザードが表示されます。

1. [ **アプリケーションの種類** ] ページで、[ **ダイアログベース]** を選択します。

1. [ **高度な機能** ] ページで、[ **Automation**] を選択し、[ **完了**] をクリックします。

> [!NOTE]
> でを追加した場合、アプリケーションはオートメーションサポートを必要としません `CoInitialize` `CTestProvApp::InitInstance` 。

[ **TestProv** ] ダイアログボックス (IDD_TESTPROV_DIALOG) を表示および編集するには **リソースビュー** でそれを選択します。 ダイアログボックスで、行セット内の文字列ごとに1つずつ、2つのリストボックスを配置します。  + リストボックスが選択されているときに Alt **enter** キーを押し、 **sort** プロパティを **False** に設定して、両方のリストボックスの並べ替えプロパティを無効にします。 また、ダイアログボックスに [ **実行** ] ボタンを配置して、ファイルをフェッチします。 [完了した **TestProv** ] ダイアログボックスには、それぞれ "string 1" と "string 2" というラベルが付いた2つのリストボックスがあります。また、 **[OK]**、 **[キャンセル**]、および [ **実行** ] ボタンもあります。

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

このコードは、行セット内の列を定義するユーザーレコードを表します。 クライアントは、を呼び出すと `IAccessor::CreateAccessor` 、これらのエントリを使用して、バインドする列を指定します。 OLE DB コンシューマーテンプレートでは、列を動的にバインドすることもできます。 COLUMN_ENTRY マクロは、PROVIDER_COLUMN_ENTRY マクロのクライアント側バージョンです。 2つの COLUMN_ENTRY マクロは、2つの文字列の序数、型、長さ、およびデータメンバーを指定します。

**Ctrl** キーを押しながら [**実行**] ボタンをダブルクリックして、[**実行**] ボタンのハンドラー関数を追加します。 関数に次のコードを配置します。

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

`CCommand`、 `CDataSource` 、およびの各クラスは `CSession` すべて OLE DB のコンシューマーテンプレートに属しています。 各クラスは、プロバイダー内の COM オブジェクトを模倣しています。 オブジェクトは、 `CCommand` `CProvider` ヘッダーファイルで宣言されているクラスをテンプレートパラメーターとして受け取ります。 パラメーターは、 `CProvider` プロバイダーからのデータにアクセスするために使用するバインディングを表します。

各クラスを開く行によって、プロバイダーに各 COM オブジェクトが作成されます。 プロバイダーを検索するには、 `ProgID` プロバイダーのを使用します。 を取得するには、 `ProgID` システムレジストリから、またはカスタムの .rgs ファイルを探します (プロバイダーのディレクトリを開き、キーを検索し `ProgID` ます)。

このサンプルには、MyData.txt ファイルが含まれてい `MyProv` ます。 独自のファイルを作成するには、エディターを使用して、文字列の間に **enter** キーを押して、偶数の文字列を入力します。 ファイルを移動する場合は、パス名を変更します。

行に "c: \\ \ samples \myprov\MyData.txt" という文字列を渡し \\ \\ `table.Open` ます。 呼び出しにステップインすると `Open` 、この文字列がプロバイダーのメソッドに渡されることがわかり `SetCommandText` ます。 メソッドでは、その文字列が使用されていることに注意 `ICommandText::Execute` してください。

データをフェッチするには、 `MoveNext` テーブルでを呼び出します。 `MoveNext` 、、およびの各関数を呼び出し `IRowset::GetNextRows` `GetRowCount` `GetData` ます。 行がなくなった場合 (つまり、行セットの現在位置がを超える場合 `GetRowCount` )、ループは終了します。

行がなくなった場合、プロバイダーは DB_S_ENDOFROWSET を返します。 DB_S_ENDOFROWSET 値がエラーではありません。 データフェッチループをキャンセルし、SUCCEEDED マクロを使用しないようにするには、常に S_OK をチェックする必要があります。

これで、プログラムをビルドしてテストできるようになります。

## <a name="see-also"></a>関連項目

[単純な Read-Only プロバイダーの拡張](../../data/oledb/enhancing-the-simple-read-only-provider.md)
