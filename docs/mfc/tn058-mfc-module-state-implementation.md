---
title: 'テクニカル ノート 58: MFC のモジュール状態の実装'
ms.date: 06/28/2018
helpviewer_keywords:
- thread state [MFC]
- module states [MFC], managing state data
- TN058
- MFC, managing state data
- module states [MFC], switching
- DLLs [MFC], module states
- process state [MFC]
ms.assetid: 72f5b36f-b3da-4009-a144-24258dcd2b2f
ms.openlocfilehash: b64fb6b97474007c44a2124315e83e1ac119f9ec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366606"
---
# <a name="tn058-mfc-module-state-implementation"></a>テクニカル ノート 58: MFC のモジュール状態の実装

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

このテクニカル ノートでは、MFC の "モジュール状態" 構造の実装について説明します。 DLL (または OLE インプロセス サーバー) から MFC 共有 DLL を使用する場合は、モジュール状態の実装を理解することが重要です。

この注を読む前に、[新しいドキュメント、Windows、およびビューの作成](../mfc/creating-new-documents-windows-and-views.md)の「MFC モジュールの状態データの管理」を参照してください。 この記事には、このテーマに関する重要な利用状況情報と概要情報が記載されています。

## <a name="overview"></a>概要

MFC の状態情報には、モジュールの状態、プロセスの状態、およびスレッドの状態の 3 種類があります。 これらの状態タイプを組み合わせることができる場合もあります。 たとえば、MFC のハンドル マップは、モジュール ローカルとスレッド ローカルの両方です。 これにより、2 つの異なるモジュールがそれぞれのスレッドに異なるマップを持つことができます。

プロセスの状態とスレッドの状態は似ています。 これらのデータ項目は、従来はグローバル変数であったものの、適切な Win32s サポートまたは適切なマルチスレッドサポートのために、特定のプロセスまたはスレッドに固有である必要があります。 特定のデータ項目がどのカテゴリに適合するかは、その項目と、プロセスおよびスレッドの境界に関する必要なセマンティクスによって異なります。

モジュール状態は、真のグローバル状態またはプロセス ローカルまたはスレッド ローカルの状態を含むことができるという意味で一意です。 また、迅速に切り替えが可能です。

## <a name="module-state-switching"></a>モジュール状態切り替え

各スレッドには、"現在" または "アクティブ" モジュールの状態へのポインターが含まれています (当然ながら、ポインターは MFC のスレッドのローカル状態の一部です)。 このポインターは、実行スレッドがモジュール境界 (OLE コントロールまたは DLL への呼び出し、アプリケーションへの呼び出しなどの OLE コントロール) を渡すと変更されます。

現在のモジュールの状態は、`AfxSetModuleState`を呼び出すことによって切り替えられます。 ほとんどの場合、API を直接処理することはありません。 MFC は、多くの場合、(WinMain、OLE エントリ ポイント`AfxWndProc`など) で、それを呼び出します。 これは、特別`WndProc`な の静的リンクによって記述するコンポーネントと、どのモジュールの状態が`WinMain`現在の`DllMain`状態かを知っている特別な (または) で行われます。 このコードは DLLMODUL を見るとわかります。CPP またはアプリケーションモジュル。MFC\SRC ディレクトリ内の CPP。

モジュールの状態を設定し、その後に設定し直さない場合は、まれです。 ほとんどの場合、自分のモジュールの状態を現在の状態として "プッシュ" し、完了後に元のコンテキストを "ポップ" します。 これは、マクロ[AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state)と特殊クラス`AFX_MAINTAIN_STATE`によって行われます。

`CCmdTarget`には、モジュール状態切り替えをサポートするための特別な機能があります。 特に、a`CCmdTarget`は OLE オートメーションと OLE COM エントリ ポイントに使用されるルート クラスです。 システムに公開されている他のエントリ ポイントと同様に、これらのエントリ ポイントは正しいモジュール状態を設定する必要があります。 「正しい」`CCmdTarget`モジュールの状態が何であるかをどのように知っているのか答えは、それが構築されたときに「現在の」モジュールの状態が何であるかを「記憶」し、後で呼び出されたときに現在のモジュール状態をその「記憶」値に設定することができるということです。 その結果、特定`CCmdTarget`のオブジェクトが関連付けられているモジュール状態は、オブジェクトが構築されたときに現在であったモジュール状態になります。 INPROC サーバーのロード、オブジェクトの作成、およびそのメソッドの呼び出しの簡単な例を挙げてみましょう。

1. DLL は、 を使用`LoadLibrary`して OLE によって読み込まれます。

1. `RawDllMain`が最初に呼び出されます。 モジュールの状態を DLL の既知の静的モジュール状態に設定します。 このため`RawDllMain`、DLL に静的にリンクされています。

1. オブジェクトに関連付けられたクラス ファクトリのコンストラクターが呼び出されます。 `COleObjectFactory`はから`CCmdTarget`派生し、その結果、インスタンス化されたモジュール状態を記憶します。 これは重要です- クラス ファクトリがオブジェクトを作成するように求められたときに、現在のモジュール状態を知るようになりました。

1. `DllGetClassObject`クラス ファクトリを取得するために呼び出されます。 MFC は、このモジュールに関連付けられているクラス ファクトリ リストを検索し、それを返します。

1. `COleObjectFactory::XClassFactory2::CreateInstance` が呼び出されます オブジェクトを作成して返す前に、この関数は、モジュールの状態を、ステップ 3 (インスタンス化されたときに`COleObjectFactory`現在の状態であったモジュール状態) に設定します。 これは[METHOD_PROLOGUE](com-interface-entry-points.md)の内部で行われます。

1. オブジェクトが作成されるとき、オブジェクトも`CCmdTarget`派生物であり、どのモジュール状態がアクティブ`COleObjectFactory`であったかを記憶するのと同じ方法で、この新しいオブジェクトも同様です。 これで、オブジェクトは呼び出されるたびにどのモジュール状態に切り替える必要があるかを知ります。

1. クライアントは、その呼び出しから受け取った`CoCreateInstance`OLE COM オブジェクトの関数を呼び出します。 オブジェクトが呼び出されると、`METHOD_PROLOGUE`モジュールの状態を同様に切`COleObjectFactory`り替えるために使用されます。

ご覧のとおり、モジュールの状態はオブジェクトからオブジェクトに作成されると伝播されます。 モジュールの状態を適切に設定することが重要です。 この値が設定されていない場合、DLL または COM オブジェクトは、DLL または COM オブジェクトを呼び出している MFC アプリケーションとの対話が適切でないか、または独自のリソースを見つけられなかったり、他の不適切な方法で失敗したりする可能性があります。

特定の種類の DLL、具体的には "MFC 拡張" DLL はモジュールの状態を`RawDllMain`切り替えない点に注意してください (`RawDllMain`実際には、 ) は通常は . これは、それらが使用するアプリケーションに実際に存在しているかのように"動作する"ためです。 これらは、実行されているアプリケーションの非常に一部であり、そのアプリケーションのグローバル状態を変更することを意図しています。

OLE コントロールと他の DLL は大きく異なります。 呼び出し元アプリケーションの状態は変更しません。呼び出しているアプリケーションは MFC アプリケーションでなくても、変更する状態がない可能性があります。 これが、モジュール状態切り替えが発明された理由です。

DLL でダイアログ ボックスを起動する関数など、DLL からエクスポートされた関数の場合は、関数の先頭に次のコードを追加する必要があります。

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState())
```

これにより、現在のモジュールの状態が、現在のスコープの終了まで[AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)から返された状態とスワップされます。

dll のリソースに関する問題は、AFX_MODULE_STATE マクロを使用しないと発生します。 既定では、MFC はメイン アプリケーションのリソース ハンドルを使用してリソース テンプレートを読み込みます。 このテンプレートは、実際には DLL に格納されます。 根本的な原因は、MFC のモジュール状態情報がAFX_MODULE_STATE マクロによって切り替えられていなくなることです。 リソース ハンドルは MFC のモジュールの状態から回復されます。 モジュールの状態を切り替えないと、間違ったリソース ハンドルが使用されます。

AFX_MODULE_STATE DLL のすべての関数に配置する必要はありません。 たとえば、MFC`InitInstance`がモジュールの状態を自動的にシフトしてから、戻り値の後`InitInstance``InitInstance`に戻すため、アプリケーション内の MFC コードからAFX_MODULE_STATE呼び出すことができます。 同じことがすべてのメッセージ マップ ハンドラにも当てはまります。 通常の MFC DLL には、メッセージをルーティングする前にモジュールの状態を自動的に切り替える特別なマスタ ウィンドウ プロシージャがあります。

## <a name="process-local-data"></a>ローカル データの処理

プロセスローカルデータは、Win32s DLLモデルの難しさがそれほど重要でなかった場合、それほど大きな懸念はありません。 Win32s では、複数のアプリケーションによって読み込まれた場合でも、すべての DLL がグローバル データを共有します。 これは、各 DLL が DLL にアタッチされる各プロセスでデータ領域の個別のコピーを取得する "実際の" Win32 DLL データ モデルとは大きく異なります。 複雑さに加えて、Win32s DLL のヒープに割り当てられたデータは、実際にはプロセス固有です (少なくとも所有権が行く限り)。 次のデータとコードを検討してください。

```cpp
static CString strGlobal; // at file scope

__declspec(dllexport)
void SetGlobalString(LPCTSTR lpsz)
{
    strGlobal = lpsz;
}

__declspec(dllexport)
void GetGlobalString(LPCTSTR lpsz, size_t cb)
{
    StringCbCopy(lpsz, cb, strGlobal);
}
```

上記のコードが DLL 内にあり、その DLL が 2 つのプロセス A と B によって読み込まれた場合に何が起こるかを考慮してください (実際には、同じアプリケーションの 2 つのインスタンスである可能性があります)。 呼び`SetGlobalString("Hello from A")`出し。 その結果、プロセス A のコンテキストで`CString`データにメモリが割り当てられます。 `CString`今Bは`GetGlobalString(sz, sizeof(sz))`. BはAが設定したデータを見ることができる。 これは、Win32s では、Win32 のようなプロセス間の保護が提供されないためです。 それが最初の問題です。多くの場合、1 つのアプリケーションが別のアプリケーションによって所有されていると見なされるグローバル データに影響を与える望ましくない場合があります。

その他の問題もあります。 Aが終了したとしましょう。 A が終了すると、 ' '`strGlobal`文字列が使用するメモリがシステムで使用できるようになります。 デストラクターが呼び出`CString`されているため、解放されません。それはまだ呼び出されていません。 割り当てたアプリケーションがシーンを離れただけで解放されます。 B が呼`GetGlobalString(sz, sizeof(sz))`び出された場合、有効なデータを取得できない可能性があります。 他のアプリケーションは、そのメモリを他の何かのために使用している可能性があります。

明らかに問題が存在します。 MFC 3.x では、スレッド ローカル ストレージ (TLS) と呼ばれる手法を使用しました。 MFC 3.x では、Win32s では、このインデックスが呼び出されず、その TLS インデックスに基づいてすべてのデータを参照する場合でも、実際にはプロセス ローカル ストレージ インデックスとして機能する TLS インデックスが割り当てられます。 これは、Win32 にスレッド ローカル データを格納するために使用された TLS インデックスに似ています (この問題の詳細については、以下を参照してください)。 これにより、すべての MFC DLL がプロセスごとに少なくとも 2 つの TLS インデックスを使用する原因となった。 多くの OLE コントロール DLL (OCX) を読み込むと、TLS インデックスが不足します (使用可能なインデックスは 64 個のみ)。 さらに、MFC では、このデータをすべて 1 つの構造で 1 か所に配置する必要がありました。 それはあまり拡張可能ではなく、TLSインデックスの使用に関しては理想的ではありませんでした。

MFC 4.x では、プロセスローカルにする必要があるデータを "ラップ" できるクラス テンプレートのセットで、このアドレスを取り上げます。 たとえば、上記の問題は、次のように記述することで解決できます。

```cpp
struct CMyGlobalData : public CNoTrackObject
{
    CString strGlobal;
};
CProcessLocal<CMyGlobalData> globalData;

__declspec(dllexport)
void SetGlobalString(LPCTSTR lpsz)
{
    globalData->strGlobal = lpsz;
}

__declspec(dllexport)
void GetGlobalString(LPCTSTR lpsz, size_t cb)
{
    StringCbCopy(lpsz, cb, globalData->strGlobal);
}
```

MFC では、この方法を 2 つの手順で実装します。 まず、Win32 __Tls\* __ API **(TlsAlloc** **、TlsSetValue、TlsGetValue**など**TlsGetValue**) の上に、DLL の数に関係なく、プロセスごとに 2 つの TLS インデックスのみを使用するレイヤーがあります。 次に、`CProcessLocal`このデータにアクセスするためのテンプレートが提供されます。 これは、上記で見る直感的な構文を可能にする演算子>をオーバーライドします。 で`CProcessLocal`ラップされるすべてのオブジェクトは、 から`CNoTrackObject`派生する必要があります。 `CNoTrackObject`は、下位レベルのアロケーター (**LocalAlloc**/**LocalFree**) と、プロセスが終了したときに MFC がプロセスローカル オブジェクトを自動的に破棄できるように、仮想デストラクターを提供します。 追加のクリーンアップが必要な場合は、このようなオブジェクトにカスタムデストラクターを設定できます。 コンパイラは埋め込み`CString`オブジェクトを破棄する既定のデストラクターを生成するため、上記の例では必要ありません。

このアプローチには他にも興味深い利点があります。 すべての`CProcessLocal`オブジェクトが自動的に破棄されるだけでなく、必要になるまで構築されません。 `CProcessLocal::operator->`は、関連付けられたオブジェクトが最初に呼び出された時点でインスタンス化されます。 上の例では、 ' '`strGlobal`文字列は最初に作成`SetGlobalString`されるか、呼`GetGlobalString`び出されるまで構築されないことを意味します。 場合によっては、DLL の起動時間を短縮できます。

## <a name="thread-local-data"></a>スレッドローカルデータ

プロセスローカルデータと同様に、スレッドローカルデータは、データが特定のスレッドに対してローカルでなければならないときに使用されます。 つまり、そのデータにアクセスするスレッドごとに、データの個別のインスタンスが必要になります。 これは、大規模な同期メカニズムの代わりに何度も使用できます。 データを複数のスレッドで共有する必要がない場合、このようなメカニズムはコストがかかり、不要になる可能性があります。 オブジェクト (上記`CString`のサンプルと同様) を持っているとします。 テンプレートでラップすることでスレッドをローカルに`CThreadLocal`できます。

```cpp
struct CMyThreadData : public CNoTrackObject
{
    CString strThread;
};
CThreadLocal<CMyThreadData> threadData;

void MakeRandomString()
{
    // a kind of card shuffle (not a great one)
    CString& str = threadData->strThread;
    str.Empty();
    while (str.GetLength() != 52)
    {
        unsigned int randomNumber;
        errno_t randErr;
        randErr = rand_s(&randomNumber);

        if (randErr == 0)
        {
            TCHAR ch = randomNumber % 52 + 1;
            if (str.Find(ch) <0)
            str += ch; // not found, add it
        }
    }
}
```

2`MakeRandomString`つの異なるスレッドから呼び出された場合、それぞれが他のスレッドに干渉することなく、異なる方法で文字列を「シャッフル」します。 これは、実際には 1`strThread`つのグローバル インスタンスではなく、スレッドごとにインスタンスが存在するためです。

ループ反復ごとに 1 回ではなく、`CString`アドレスを 1 回キャプチャするために参照がどのように使用されているかに注意してください。 ループ コードは`threadData->strThread`、どこでも ' '`str`が使用されている場合でも記述できますが、コードの実行速度は大幅に低下します。 このような参照がループで発生する場合は、データへの参照をキャッシュすることをお勧めします。

クラス`CThreadLocal`テンプレートは、同じメカニズムを`CProcessLocal`使用し、同じ実装手法を使用します。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
