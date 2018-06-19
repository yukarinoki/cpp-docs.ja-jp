---
title: 'TN026: DDX ルーチンおよび DDV ルーチン |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- DDX
- DDV
dev_langs:
- C++
helpviewer_keywords:
- DDX (dialog data exchange), procedures
- TN026
- DDV (dialog data validation), procedures
ms.assetid: c2eba87a-4b47-4083-b28b-e2fa77dfb4c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44a946b21908f45b595056a956c75b234fdbb886
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33386055"
---
# <a name="tn026-ddx-and-ddv-routines"></a>テクニカル ノート 26: DDX ルーチンおよび DDV ルーチン
> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 ここでは、ダイアログ データ エクス (チェンジ DDX) およびダイアログ データ バリデーション (DDV) のアーキテクチャについて説明します。 Ddx _ または DDV_ プロシージャを記述する方法と、ルーチンを使用する ClassWizard を拡張する方法についても説明します。  
  
## <a name="overview-of-dialog-data-exchange"></a>ダイアログ データ エクス チェンジの概要  
 すべてのダイアログ データ関数は、C++ コードによって実行されます。 マクロや特別なリソースはありません。 機構の中核部分は、仮想関数はダイアログのデータを交換するすべてのダイアログ クラスでオーバーライドされると検証はします。 このフォームに常に存在します。  
  
```  
void CMyDialog::DoDataExchange(CDataExchange* pDX)  
{  
    CDialog::DoDataExchange(pDX);
*// call base class  
 *//{{AFX_DATA_MAP(CMyDialog)  
 <data_exchange_function_call>  
 <data_validation_function_call> *//}}AFX_DATA_MAP  
}  
```  
  
 特殊なフォーマット AFX コメントでは、ClassWizard を探して、この関数内でコードを編集できるようにします。 ClassWizard と互換性がないコードは、特殊な形式のコメントの外側に配置する必要があります。  
  
 上記の例では、< data_exchange_function_call > の形式は。  
  
```  
DDX_Custom(pDX,
    nIDC,
    field);
```  
  
 され < data_validation_function_call > が省略可能な形式では。  
  
```  
DDV_Custom(pDX,
    field, ...);
```  
  
 それぞれに 1 つ以上の ddx _/ddv ペアを含めることは`DoDataExchange`関数。  
  
 すべてのダイアログ データ エクス チェンジ ルーチンと MFC に用意されているダイアログ データ検証ルーチンの一覧については、'afxdd_.h' を参照してください。  
  
 ダイアログ データは、単: にメンバーのデータ、 **CMyDialog**クラスです。 構造体または同様のものでは格納されません。  
  
## <a name="notes"></a>メモ  
 この「ダイアログ データ」と呼んで、すべての機能では利用できる任意のクラスから派生した`CWnd`だけダイアログに限定されませんとします。  
  
 データの初期値は、標準 C++ のコンス トラクターで、通常のブロック設定`//{{AFX_DATA_INIT`と`//}}AFX_DATA_INIT`コメントです。  
  
 `CWnd::UpdateData` 初期化とエラーの呼び出しを処理を行う操作は、`DoDataExchange`です。  
  
 呼び出すことができます`CWnd::UpdateData`データ交換と検証を実行するには、いつでもできます。 既定では`UpdateData`(TRUE) は、既定値で呼び出される`CDialog::OnOK`ハンドラーと`UpdateData`(FALSE) が既定値で呼び出される`CDialog::OnInitDialog`です。  
  
 DDV_ ルーチン必要がありますが、ddx _ ルーチンの直後に続く*フィールド*です。  
  
## <a name="how-does-it-work"></a>動作方法  
 ダイアログ データを使用するために、次を理解する必要はありません。 ただし、バック グラウンドでこのしくみを理解することにより、独自の exchange または検証プロシージャを記述するされます。  
  
 `DoDataExchange`メンバー関数は、非常によく似た、`Serialize`メンバー関数を取得または設定するデータを外部のフォームから (ここでは、ダイアログ ボックスで制御) から/クラスにメンバーのデータにします。 `pDX`パラメーターのデータ交換を行うためのコンテキストし、似ています、`CArchive`パラメーターを`CObject::Serialize`です。 `pDX` (、`CDataExchange`オブジェクト) が似てフラグ方向`CArchive`方向フラグします。  
  
-   場合 **! m_bSaveAndValidate**コントロールにデータの状態を読み込みます。  
  
-   場合`m_bSaveAndValidate`、コントロールからデータの状態を設定します。  
  
 検証にのみ発生時に`m_bSaveAndValidate`設定されています。 値`m_bSaveAndValidate`BOOL パラメーターによって決定されます`CWnd::UpdateData`です。  
  
 その他の 3 つの興味深いがある`CDataExchange`メンバー。  
  
- `m_pDlgWnd`: ウィンドウ (通常はダイアログ) コントロールを含むです。 これは、ddx _ および DDV_ グローバル関数の呼び出し元は 'this' を渡さずに各 DDX/DDV ルーチンにありません。  
  
- `PrepareCtrl`、および`PrepareEditCtrl`: データ交換するためのダイアログ コントロールを準備します。 検証が失敗した場合、フォーカスを設定するため、そのコントロールのハンドルを格納します。 `PrepareCtrl` エディット コントロールの使用と`PrepareEditCtrl`エディット コントロールのために使用します。  
  
- **失敗**: ユーザーが入力のエラーを警告メッセージ ボックスの後に呼び出されます。 このルーチンは、最後のコントロールにフォーカスを復元します (最後の呼び出し`PrepareCtrl` / `PrepareEditCtrl`)、例外をスローします。 このメンバー関数は、ddx _ と DDV_ の両方のルーチンから呼び出すことができます。  
  
## <a name="user-extensions"></a>ユーザーの拡張機能  
 既定の DDX/DDV メカニズムを拡張するいくつかの方法はあります。 次の操作を行うことができます。  
  
-   新しいデータ型を追加します。  
  
 ```  
    CTime 
 ```  
  
-   新しい exchange プロシージャ (ddx _) を追加します。  
  
 ```  
    void PASCAL DDX_Time(CDataExchange* pDX,
    int nIDC,
    CTime& tm);

 ```  
  
-   新しい検証プロシージャ (DDV_) を追加します。  
  
 ```  
    void PASCAL DDV_TimeFuture(CDataExchange* pDX,
    CTime tm,
    BOOL bFuture);
*// make sure time is in the future or past  
 ```  
  
-   検証手順を任意の式を渡します。  
  
 ```  
    DDV_MinMax(pDX,
    age,
    0,
    m_maxAge);

 ```  
  
    > [!NOTE]
    >  このような任意の式は ClassWizard で編集することはできず、特殊な形式のコメントの外部で移動する必要があります (//{{AFX_DATA_MAP(CMyClass)) です。  
  
 **DoDialogExchange**メンバー関数には、条件または混合交換と検証の関数呼び出しとその他の有効な C++ ステートメントが含まれます。  
  
```  
//{{AFX_DATA_MAP(CMyClass)  
DDX_Check(pDX,
    IDC_SEX,
    m_bFemale);

DDX_Text(pDX,
    IDC_EDIT1,
    m_age);

//}}AFX_DATA_MAP  
if (m_bFemale)  
    DDV_MinMax(pDX,
    age,
    0,
    m_maxFemaleAge);

else  
    DDV_MinMax(pDX,
    age,
    0,
    m_maxMaleAge);
```  
  
> [!NOTE]
>  上記のように、このようなコードは ClassWizard で編集することはできませんし、特別な形式のコメントの外側でのみ使用する必要があります。  
  
## <a name="classwizard-support"></a>ClassWizard サポート  
 ClassWizard では、ClassWizard ユーザー インターフェイスに、独自の ddx _ と DDV_ ルーチンを統合することにより DDX/DDV のカスタマイズのサブセットをサポートしています。 費用効果は、特定 DDX ルーチンおよび DDV ルーチンまたは多くのプロジェクトで、プロジェクトで再利用する予定の場合、これを行います。  
  
 これを行うには、特殊なエントリは、DDX で行われます。CLW (Visual C の以前のバージョンは、APSTUDIO にこの情報を格納します。INI) またはプロジェクトのです。CLW ファイルです。 特殊なエントリは、プロジェクトの [一般情報] セクションのいずれかを入力します。CLW ファイルまたは、DDX の [ExtraDDX] セクションでします。CLW \Program Files\Microsoft Visual Studio\Visual c++ \bin ディレクトリのファイルです。 DDX を作成する必要があります。CLW ファイルが存在しない場合です。 特定のプロジェクトにのみ、カスタムの ddx _/ddv ルーチンを使用することを計画する場合は、プロジェクトの [一般情報] セクションにエントリを追加します。CLW ファイルの代わりにします。 多くのプロジェクトで、ルーチンを使用する場合は、DDX の [ExtraDDX] セクションにエントリを追加します。CLW です。  
  
 これらの特別なエントリの一般的な形式です。  
  
```  
ExtraDDXCount=n  
```  
  
 ここで n に従う ExtraDDX 行の数  
  
```  
ExtraDDX=<keys>;<vb-keys>; <prompt>; <type>; <initValue>; <DDX_Proc>  
[;<DDV_Proc>; <prompt1>; <arg1>; [<prompt2>; <fmt2>]]  
```  
  
 ここで、1 - n DDX 型で定義されている一覧を示す数値です。  
  
 各フィールドは、';' の文字で区切られます。 フィールドとその用途を以下に示します。  
  
 \<キー >  
 どのダイアログ コントロールのこの変数の型が許可されていることを示す単一の文字の一覧を = です。  
  
 E = 編集  
  
 C = 2 つの状態のチェック ボックス  
  
 c = 3 つの状態のチェック ボックス  
  
 R、グループ内の最初のラジオ ボタンを =  
  
 L = 並べ替えずリスト ボックス  
  
 l = 並べ替えられたリスト ボックス  
  
 M = コンボ ボックス (編集のアイテムを)  
  
 N = 並べ替えずボックスの一覧  
  
 n = 並べ替えられたボックスの一覧  
  
 1 = DDX 挿入リストの先頭に追加する場合 (既定値は末尾に追加) これは、通常使用 DDX ルーチンでは、'コントロール' プロパティを転送します。  
  
 \<vb キー >  
 このフィールドは、16 ビット製品でのみ VBX コントロール (VBX コントロールは、32 ビット製品ではサポートされません) の使用します。  
  
 \<プロンプト >  
 プロパティ コンボ ボックス (引用符) で指定する文字列  
  
 \<type>  
 ヘッダー ファイルに出力する型の 1 つの識別子。 上記 DDX_Time の例では、これに設定する CTime です。  
  
 \<vb キー >  
 このバージョンでは使用されませんし、常に空でする必要があります  
  
 \<initValue >  
 初期値-0 または空です。 空白の場合は、初期化行が、実装ファイルの//{{AFX_DATA_INIT セクションに書き込まれません。 空のエントリは、C++ オブジェクトのために使用する必要があります (など`CString`、`CTime`など) ことを適切な初期化を保証するコンス トラクターがあること。  
  
 < DDX_Proc >  
 Ddx _ プロシージャの 1 つの識別子。 C++ 関数の名前は、"DDX"で開始する必要がありますが、< DDX_Proc > 識別子に「ddx _」を含めません。 上記の例では、< DDX_Proc > 識別子を時間となります。 ClassWizard が、実装ファイル内に関数呼び出しを記述するときに、{{AFX_DATA_MAP セクションで、この名に追加 DDX したがって DDX_Time に到着します。  
  
 \<コメント >  
 この DDX と変数のダイアログ ボックスに表示するコメントです。 ここであり、通常の機能が提供したい DDX/DDV ペアによって実行される操作について説明するテキストを配置します。  
  
 < DDV_Proc >  
 エントリの DDV 部分は省略できます。 すべての DDX ルーチンでは、対応する DDV ルーチンがあります。 多くの場合、転送の一環として、検証フェーズを含める方が便利です。 これは多くの場合、大文字と小文字 DDV ルーチンは、すべてのパラメーターを必要としないときに ClassWizard では、パラメーターを使用せず DDV ルーチンをサポートしていないためです。  
  
 \<arg >  
 DDV_ プロシージャの 1 つの識別子。 C++ の関数名は"DDV_"で始める必要が、id に、< DDX_Proc >「ddx _」は含めないでください。  
  
 DDV 引数を 1 つまたは 2 が続きます。  
  
 \<promptX >  
 文字列編集項目 (& accelerator) の上に配置するには  
  
 \<fmtX >  
 引数型のいずれかの形式の文字  
  
 d = int  
  
 u = 符号なし  
  
 D (つまり、長い)、long int を =  
  
 U = 符号なし長 (つまり、DWORD)  
  
 f = float  
  
 F = 倍精度浮動小数点  
  
 s = 文字列  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

