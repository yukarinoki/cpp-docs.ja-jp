---
description: '詳細については、「テクニカルノート 26: DDX ルーチンと DDV ルーチン」を参照してください。'
title: 'テクニカル ノート 26: DDX ルーチンおよび DDV ルーチン'
ms.date: 06/28/2018
f1_keywords:
- DDX
- DDV
helpviewer_keywords:
- DDX (dialog data exchange), procedures
- TN026
- DDV (dialog data validation), procedures
ms.assetid: c2eba87a-4b47-4083-b28b-e2fa77dfb4c4
ms.openlocfilehash: 1e5c8d3679b7e91ad7f356c1e6f6badc61cdd46f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215704"
---
# <a name="tn026-ddx-and-ddv-routines"></a>テクニカル ノート 26: DDX ルーチンおよび DDV ルーチン

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

このメモでは、ダイアログデータエクスチェンジ (DDX) およびダイアログデータ検証 (DDV) アーキテクチャについて説明します。 また、DDX_ または DDV_ の手順を記述する方法、および ClassWizard を拡張してルーチンを使用する方法についても説明します。

## <a name="overview-of-dialog-data-exchange"></a>ダイアログデータエクスチェンジの概要

すべてのダイアログデータ関数は、C++ コードで実行されます。 特別なリソースやマジックマクロはありません。 このメカニズムの中核となるのは、ダイアログデータエクスチェンジと検証を行うすべてのダイアログクラスでオーバーライドされる仮想関数です。 次の形式で常に検出されます。

```cpp
void CMyDialog::DoDataExchange(CDataExchange* pDX)
{
    CDialog::DoDataExchange(pDX);   // call base class

    //{{AFX_DATA_MAP(CMyDialog)
        <data_exchange_function_call>
        <data_validation_function_call>
    //}}AFX_DATA_MAP
}
```

特別な形式の AFX コメントを使用すると、ClassWizard はこの関数内のコードを検索して編集できます。 ClassWizard と互換性のないコードは、特別な形式のコメントの外部に配置する必要があります。

上の例で \<data_exchange_function_call> は、は次の形式になっています。

```cpp
DDX_Custom(pDX, nIDC, field);
```

と \<data_validation_function_call> は省略可能で、という形式になっています。

```cpp
DDV_Custom(pDX, field, ...);
```

各関数には、複数の DDX_/DDV_ ペアを含めることができ `DoDataExchange` ます。

MFC に用意されているダイアログデータエクスチェンジルーチンとダイアログデータ検証ルーチンの一覧については、「afxdd_」を参照してください。

ダイアログデータは、クラス内のメンバーデータにすぎ `CMyDialog` ません。 構造体またはそれに類似したものには格納されません。

## <a name="notes"></a>メモ

この "ダイアログデータ" と呼ばれますが、のすべての機能は、から派生したすべてのクラスで使用でき `CWnd` 、ダイアログだけに限定されるわけではありません。

データの初期値は、標準 C++ コンストラクターで設定されます。通常は、とのコメントが含まれるブロックに `//{{AFX_DATA_INIT` `//}}AFX_DATA_INIT` あります。

`CWnd::UpdateData` は、の呼び出しを囲む初期化とエラー処理を実行する操作です `DoDataExchange` 。

いつ `CWnd::UpdateData` でもを呼び出して、データ交換と検証を実行できます。 既定で `UpdateData` は (TRUE) が既定のハンドラーで呼び出され、 `CDialog::OnOK` `UpdateData` (FALSE) が既定で呼び出され `CDialog::OnInitDialog` ます。

DDV_ ルーチンは、その *フィールド* の DDX_ ルーチンの直後にある必要があります。

## <a name="how-does-it-work"></a>動作のしくみ

ダイアログデータを使用するために、次のことを理解する必要はありません。 ただし、これがバックグラウンドでどのように動作するかを理解することは、独自の exchange または検証の手順を記述するのに役立ちます。

`DoDataExchange`メンバー関数は、メンバー関数とよく似ています。このメンバー関数は、 `Serialize` 外部フォーム (この場合はダイアログのコントロール) からクラスのメンバーデータへのデータの取得や設定を行います。 *PDX* パラメーターは、データ交換を実行するためのコンテキストであり、のパラメーターに似てい `CArchive` `CObject::Serialize` ます。 *PDX* (オブジェクト) には、方向フラグがあるの `CDataExchange` と同じような方向フラグがあり `CArchive` ます。

- の場合は、 `!m_bSaveAndValidate` データ状態をコントロールに読み込みます。

- の場合は、 `m_bSaveAndValidate` コントロールからデータの状態を設定します。

検証は、が設定されている場合にのみ発生し `m_bSaveAndValidate` ます。 の値は、の `m_bSaveAndValidate` BOOL パラメーターによって決定され `CWnd::UpdateData` ます。

他にも、次の3つの興味深いメンバーがあり `CDataExchange` ます。

- `m_pDlgWnd`: コントロールが含まれているウィンドウ (通常はダイアログ)。 これは、DDX_ および DDV_ のグローバル関数の呼び出し元が、' this ' をすべての DDX/DDV ルーチンに渡す必要がないようにするためです。

- `PrepareCtrl`、、および `PrepareEditCtrl` : データ交換のダイアログコントロールを準備します。 検証が失敗した場合にフォーカスを設定するためのコントロールのハンドルを格納します。 `PrepareCtrl` は、非編集コントロールに使用され、 `PrepareEditCtrl` エディットコントロールに使用されます。

- `Fail`: 入力エラーをユーザーに警告するメッセージボックスを表示した後に呼び出されます。 このルーチンは、最後のコントロール (またはへの最後の呼び出し) にフォーカスを復元 `PrepareCtrl` `PrepareEditCtrl` し、例外をスローします。 このメンバー関数は、DDX_ と DDV_ の両方のルーチンから呼び出すことができます。

## <a name="user-extensions"></a>ユーザー拡張機能

既定の DDX/DDV 機構を拡張するには、いくつかの方法があります。 次のようにすることができます。

- 新しいデータ型を追加します。

    ```cpp
    CTime
    ```

- 新しい exchange プロシージャを追加します (DDX_)。

    ```cpp
    void PASCAL DDX_Time(CDataExchange* pDX, int nIDC, CTime& tm);
    ```

- 新しい検証プロシージャ (DDV_) を追加します。

    ```cpp
    void PASCAL DDV_TimeFuture(CDataExchange* pDX, CTime tm, BOOL bFuture);
    // make sure time is in the future or past
    ```

- 任意の式を検証プロシージャに渡します。

    ```cpp
    DDV_MinMax(pDX, age, 0, m_maxAge);
    ```

    > [!NOTE]
    > このような任意の式は、ClassWizard では編集できないため、特殊な形式のコメント (//{{AFX_DATA_MAP (CMyClass)) の外に移動する必要があります。

このメンバー関数には、 `DoDialogExchange` exchange と検証の関数呼び出しを含む、条件またはその他の有効な C++ ステートメントが含まれている必要があります。

```cpp
//{{AFX_DATA_MAP(CMyClass)
DDX_Check(pDX, IDC_SEX, m_bFemale);
DDX_Text(pDX, IDC_EDIT1, m_age);
//}}AFX_DATA_MAP
if (m_bFemale)
    DDV_MinMax(pDX, age, 0, m_maxFemaleAge);
else
    DDV_MinMax(pDX, age, 0, m_maxMaleAge);
```

> [!NOTE]
> 上記のように、このようなコードは、ClassWizard で編集することはできません。また、特殊な書式のコメント以外でのみ使用してください。

## <a name="classwizard-support"></a>ClassWizard のサポート

ClassWizard は、独自の DDX_ と DDV_ ルーチンを ClassWizard ユーザーインターフェイスに統合できるようにすることで、DDX/DDV のカスタマイズのサブセットをサポートしています。 これは、プロジェクトまたは多くのプロジェクトで特定の DDX ルーチンおよび DDV ルーチンを再利用する予定がある場合にのみ、コスト効果があります。

これを行うには、(以前のバージョンの Visual C++ この情報を APSTUDIO.INI) またはプロジェクトのに格納します。CLW ファイル。 特別なエントリは、プロジェクトのの [全般情報] セクションで入力できます。CLW ファイルまたは、Studio\Visual ファイルの [ExtraDDX] セクションで、このファイルを参照してください。 まだ存在しない場合は、そのファイルを作成する必要があります。 カスタム DDX_/DDV_ ルーチンを特定のプロジェクトでのみ使用する場合は、プロジェクトの [General Info] セクションにエントリを追加します。代わりに CLW ファイル。 多くのプロジェクトでルーチンを使用する予定がある場合は、そのエントリを [Extrw] の [ExtraDDX] セクションに追加します。

これらの特殊なエントリの一般的な形式は次のとおりです。

> ExtraDDXCount =*n*

ここで、 *n* は ExtraDDX の数ですか?[次の形式で実行する行]

> ExtraDDX? =*キー*; *vb-キー*; *プロンプト* を表示します。 *「*」と入力します。 *Initvalue*; *DDX_Proc* [; *DDV_Proc*; *prompt1*; *arg1* [; *prompt2*; *fmt2*]]

どこ。 定義されているリスト内のどの DDX 型であるかを示す 1 ~ *n* の数値を指定します。

各フィールドは、'; ' 文字で区切られます。 以下では、フィールドとその用途について説明します。

- *鍵*

  この変数の型が許可されるダイアログコントロールを示す単一の文字のリスト。

  |文字|許可されるコントロール|
  |-|-|
  E | 編集
  C | 2つの状態のチェックボックス
  c | [トライステート] チェックボックス
  R | グループ内の最初のオプションボタン
  L | 並べ替えられていないリストボックス
  l | 並べ替えられたリストボックス
  M | コンボボックス (編集項目付き)
  × | 並べ替えられていないドロップリスト
  n | 並べ替えられたドロップリスト
  1 | DDX 挿入をリストの先頭に追加する必要がある場合 (既定値は tail に追加される)、これは通常、' Control ' プロパティを転送する DDX ルーチンで使用されます。

- *vb-キー*

  このフィールドは、VBX コントロールの16ビット製品でのみ使用されます (VBX コントロールは32ビット製品ではサポートされていません)

- *prompt*

  プロパティコンボボックスに配置する文字列 (引用符なし)

- *type*

  ヘッダーファイルに出力する型の単一の識別子。 上の例の DDX_Time を使用すると、これは CTime に設定されます。

- *vb-キー*

  このバージョンでは使用されず、常に空である必要があります

- *initValue*

  初期値: 0 または空白。 空白の場合は、実装ファイルの//{{AFX_DATA_INIT セクションに初期化行が書き込まれません。 `CString`正しい初期化を保証するコンストラクターを持つ C++ オブジェクト (、など) には空白のエントリを使用する必要があり `CTime` ます。

- *DDX_Proc*

  DDX_ プロシージャの単一識別子。 C++ の関数名は "DDX_" で始める必要がありますが、識別子に "DDX_" は含めないでください \<DDX_Proc> 。 上記の例では、 \<DDX_Proc> 識別子は Time です。 ClassWizard が {{AFX_DATA_MAP セクションの実装ファイルに関数呼び出しを書き込むと、この名前が DDX_ に追加されるため、DDX_Time に到達します。

- *comment*

  この DDX の変数のダイアログに表示するコメント。 ここに任意のテキストを配置します。通常は、DDX/DDV のペアによって実行される操作を説明するものを指定します。

- *DDV_Proc*

  エントリの DDV 部分は省略可能です。 すべての DDX ルーチンに対応する DDV ルーチンがあるわけではありません。 多くの場合、検証フェーズを、転送の不可欠な部分として含める方が便利です。 このような場合、ClassWizard ではパラメーターを指定せずに DDV ルーチンがサポートされないため、これは多くの場合、DDV ルーチンでパラメーターを必要としない場合に発生します。

- *arg*

  DDV_ プロシージャの単一識別子。 C++ の関数名は "DDV_" で始める必要がありますが、識別子に "DDX_" は含めないでください \<DDX_Proc> 。

  *arg* の後に1または2つの DDV 引数が続きます。

  - *promptN*

      編集項目の上に配置する文字列 (アクセラレータの場合は &)。

  - *fmtN*

      Arg 型の書式文字。次のいずれかになります。

      |文字|Type|
      |-|-|
      |d | INT|
      |u | unsigned int|
      |D | long int (つまり long)|
      |U | long unsigned (DWORD)|
      |f | float|
      |F | double|
      |s | string|

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
