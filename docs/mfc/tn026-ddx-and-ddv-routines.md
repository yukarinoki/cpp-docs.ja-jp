---
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
ms.openlocfilehash: 711d433b51ca09836f372d09a11f86c28b82cce6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370348"
---
# <a name="tn026-ddx-and-ddv-routines"></a>テクニカル ノート 26: DDX ルーチンおよび DDV ルーチン

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

この注では、ダイアログ データ エクスチェンジ (DDX) およびダイアログ データ検証 (DDV) アーキテクチャについて説明します。 また、DDX_またはDDV_プロシージャを記述する方法と、ClassWizard を拡張してルーチンを使用する方法についても説明します。

## <a name="overview-of-dialog-data-exchange"></a>ダイアログ データ エクスチェンジの概要

ダイアログ データ関数はすべて C++ コードで行います。 特別なリソースや魔法のマクロはありません。 メカニズムの中心は、ダイアログ データ交換と検証を行うすべてのダイアログ クラスでオーバーライドされる仮想関数です。 このフォームは常に次の形式で見つかります。

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

特殊形式の AFX コメントを使用すると、ClassWizard はこの関数内のコードを検索して編集できます。 ClassWizard と互換性のないコードは、特殊な形式のコメントの外側に配置する必要があります。

上の例では、>data_exchange_function_call\<形式になります。

```cpp
DDX_Custom(pDX, nIDC, field);
```

data_validation_function_call>\<はオプションで、次の形式で指定します。

```cpp
DDV_Custom(pDX, field, ...);
```

各`DoDataExchange`関数には、複数のDDX_/DDV_のペアを含める場合があります。

MFC で提供されるすべてのダイアログ データ エクスチェンジ ルーチンとダイアログ データ検証ルーチンの一覧については、'afxdd_.h' を参照してください。

ダイアログ データは、`CMyDialog`クラスのメンバ データだけです。 構造体または同様の何かに格納されません。

## <a name="notes"></a>Notes

これを「ダイアログ データ」と呼んでいますが、すべての機能は、派生`CWnd`したクラスで使用でき、ダイアログだけに限定されません。

データの初期値は、標準の C++ コンストラクタで`//{{AFX_DATA_INIT``//}}AFX_DATA_INIT`設定されます。

`CWnd::UpdateData`は、 への呼び出しを中心に初期化とエラー処理`DoDataExchange`を行う操作です。

いつでも呼び`CWnd::UpdateData`出して、データ交換と検証を実行できます。 既定`UpdateData`では (TRUE) は既定`CDialog::OnOK`のハンドラーで`UpdateData`呼び出され、(FALSE)`CDialog::OnInitDialog`は既定で呼び出されます。

DDV_ ルーチンは、その*フィールド*のDDX_ ルーチンの直後に続く必要があります。

## <a name="how-does-it-work"></a>どのように動作しますか

ダイアログ データを使用するために、次のことを理解する必要はありません。 ただし、この動作をバックグラウンドで理解することは、独自の交換または検証手順を記述するのに役立ちます。

`DoDataExchange`メンバー関数は`Serialize`、メンバー関数と似ていますが、外部フォーム (この場合はダイアログ内のコントロール) との間で、クラス内のメンバー データとの間でデータを取得または設定する役割を担います。 *pDX*パラメータは、データ交換を行うためのコンテキストであり、`CArchive`パラメータと似ています`CObject::Serialize`。 *pDX(*`CDataExchange`オブジェクト)には方向フラグ`CArchive`が付いています。

- の`!m_bSaveAndValidate`場合は、データ状態をコントロールに読み込みます。

- の`m_bSaveAndValidate`場合は、コントロールのデータ状態を設定します。

検証は、設定されている`m_bSaveAndValidate`場合にのみ実行されます。 の`m_bSaveAndValidate`値は、BOOL パラメータによって決定されます`CWnd::UpdateData`。

他にも興味深い`CDataExchange`メンバーが3つあります。

- `m_pDlgWnd`: コントロールを含むウィンドウ (通常はダイアログ) です。 これは、DDX_の呼び出し元とDDV_グローバル関数が、すべての DDX/DDV ルーチンに 'this' を渡す必要がないようにするためです。

- `PrepareCtrl`、および`PrepareEditCtrl`: データ交換用のダイアログ コントロールを準備します。 検証が失敗した場合にフォーカスを設定するためのコントロールのハンドルを格納します。 `PrepareCtrl`は非編集コントロールに使用され、`PrepareEditCtrl`エディット コントロールに使用されます。

- `Fail`: ユーザーに入力エラーを通知するメッセージ ボックスを表示した後に呼び出されます。 このルーチンは、フォーカスを最後のコントロール (または への最後`PrepareCtrl`の`PrepareEditCtrl`呼び出し) に復元し、例外をスローします。 このメンバー関数は、DDX_ ルーチンとDDV_ ルーチンの両方から呼び出される場合があります。

## <a name="user-extensions"></a>ユーザー拡張機能

デフォルトの DDX/DDV メカニズムを拡張するには、いくつかの方法があります。 次のようにすることができます。

- 新しいデータ型を追加します。

    ```cpp
    CTime
    ```

- 新しい交換手順を追加します (DDX_)。

    ```cpp
    void PASCAL DDX_Time(CDataExchange* pDX, int nIDC, CTime& tm);
    ```

- 新しい検証手順を追加します (DDV_)。

    ```cpp
    void PASCAL DDV_TimeFuture(CDataExchange* pDX, CTime tm, BOOL bFuture);
    // make sure time is in the future or past
    ```

- 検証プロシージャに任意の式を渡します。

    ```cpp
    DDV_MinMax(pDX, age, 0, m_maxAge);
    ```

    > [!NOTE]
    > このような任意の式は ClassWizard で編集できないため、特殊な形式のコメント (//{{{AFX_DATA_MAP (CMyClass)) の外に移動する必要があります。

`DoDialogExchange`条件付きの条件を含めるか、または交換と検証関数の呼び出しが混在するその他の有効な C++ ステートメントをメンバー関数に含めます。

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
> 上に示したように、このようなコードは ClassWizard で編集することはできず、特別な形式のコメントの外でのみ使用してください。

## <a name="classwizard-support"></a>クラスウィザードのサポート

クラス ウィザードは、独自のDDX_とDDV_ ルーチンを ClassWizard ユーザー インターフェイスに統合できるようにすることで、DDX/DDV のカスタマイズのサブセットをサポートします。 これは、プロジェクトまたは多くのプロジェクトで特定の DDX ルーチンと DDV ルーチンを再利用する場合にのみコストを有効にします。

これを行うには、DDX で特別なエントリが作成されます。CLW (以前のバージョンの Visual C++ では、この情報は APSTUDIO に格納されています。INI) またはプロジェクトの .CLW ファイル。 特殊なエントリは、プロジェクトの [一般情報] セクションに入力できます。CLW ファイルまたは DDX の [エクストラDDX] セクションに。\プログラム ファイル\マイクロソフト ビジュアル スタジオ\Visual C++\bin ディレクトリ内の CLW ファイル。 DDX を作成する必要がある場合があります。CLW ファイルが存在しない場合は、ファイルを指定します。 特定のプロジェクトでのみカスタム DDX_/DDV_ ルーチンを使用する場合は、プロジェクトの [全般情報] セクションにエントリを追加します。代わりに CLW ファイル。 多くのプロジェクトでルーチンを使用する場合は、DDX の [ExtraDDX] セクションにエントリを追加します。CLW.

これらの特殊なエントリの一般的な形式は次のとおりです。

> エクストラドDXカウント=*n*

*n*はエクストラ DDX の数は?フォームの後に続く行

> エクストラDDX?=*キー*;*vb キー*;*プロンプト*;*型*;*イニトバリュー*;*DDX_Proc* [;*DDV_Proc*;*プロンプト1;**arg1* [;*プロンプト2;**fmt2]]*

どこ。 は、定義されているリスト内の DDX タイプを示す数値 1 - *n*です。

各フィールドは';' 文字で区切られます。 フィールドとその目的を以下に説明します。

- *キー*

  この変数の種類を制御するダイアログを示す単一文字のリストが許可されます。

  |文字|許可された制御|
  |-|-|
  E | 編集
  C | [2 状態] チェック ボックス
  c | [トライステート] チェック ボックス
  R | グループ内の最初のラジオボタン
  L | 並べ替えなしリスト ボックス
  l | 並べ替えられたリスト ボックス
  M | コンボ ボックス (アイテムの編集)
  N | 並べ替えなしのドロップ リスト
  n | 並べ替えられたドロップ リスト
  1 | DDX 挿入がリストの先頭に追加する必要がある場合 (既定は末尾に追加) これは、一般的に 'Control' プロパティを転送する DDX ルーチンに使用されます。

- *vb キー*

  このフィールドは、VBX コントロールの 16 ビット製品でのみ使用されます (VBX コントロールは 32 ビット製品ではサポートされていません)

- *プロンプト*

  プロパティコンボボックスに配置する文字列(引用符なし)

- *type*

  ヘッダー ファイルに出力する型の単一識別子。 上記のDDX_Timeの例では、これは CTime に設定されます。

- *vb キー*

  このバージョンでは使用されず、常に空である必要があります

- *イニトバリュー*

  初期値 : 0 または空白。 空白の場合、実装ファイルの //{{AFX_DATA_INIT セクションに初期化行は書き込まれません。 正しい初期化を保証するコンストラクターを持つ C++ `CString``CTime`オブジェクト ( など ) には、空のエントリを使用する必要があります。

- *DDX_Proc*

  DDX_ プロシージャの単一識別子。 C++ 関数名は "DDX_" で始まる必要がありますが\<、DDX_Proc>識別子に "DDX_" を含めないでください。 上の例では、DDX_Proc>\<識別子は Time になります。 ClassWizard は、{{AFX_DATA_MAP セクションの実装ファイルに関数呼び出しを書き込むときに、DDX_にこの名前を追加して、DDX_Timeに到着します。

- *comment*

  この DDX を使用して変数のダイアログに表示するコメント。 ここに必要なテキストを配置し、通常は DDX/DDV ペアで実行される操作を説明する内容を指定します。

- *DDV_Proc*

  エントリの DDV 部分は省略可能です。 すべての DDX ルーチンに対応する DDV ルーチンがあるわけではありません。 多くの場合、検証フェーズを転送の不可欠な部分として含める方が便利です。 ClassWizard はパラメーターなしの DDV ルーチンをサポートしていないため、DDV ルーチンがパラメーターを必要としない場合によくあるケースです。

- *Arg*

  DDV_ プロシージャの単一識別子。 C++ 関数名は"DDV_"で始まる必要がありますが\<、DDX_Proc>識別子に "DDX_" を含めないでください。

  *arg*の後に 1 つまたは 2 つの DDV args が続きます。

  - *プロンプトN*

      編集項目の上に配置する文字列 (アクセラレータの&)。

  - *fmtN*

      arg 型の書式指定文字 (次のいずれか)。

      |文字|Type|
      |-|-|
      |d | INT|
      |u | unsigned int|
      |D | 長い整数 (つまり、長い)|
      |U | 長い符号なし (つまり、DWORD)|
      |f | float|
      |F | double|
      |s | string|

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
