---
title: 'TN058: MFC モジュール状態の実装 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.implementation
dev_langs:
- C++
helpviewer_keywords:
- thread state [MFC]
- module states [MFC], managing state data
- TN058
- MFC, managing state data
- module states [MFC], switching
- DLLs [MFC], module states
- process state [MFC]
ms.assetid: 72f5b36f-b3da-4009-a144-24258dcd2b2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 662ac381fe5513747795f38866172e6dea6fdb03
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121992"
---
# <a name="tn058-mfc-module-state-implementation"></a>テクニカル ノート 58: MFC のモジュール状態の実装

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

このテクニカル ノートでは、MFC「モジュールの状態」コンストラクトの実装について説明します。 共有 DLL から Dll を MFC を使用してモジュールの状態の実装の理解が重要な (または OLE インプロセス サーバー)。

このノートを読む前に参照してください「の管理モジュールの状態データの MFC モジュール」で[ドキュメントを新規に作成する、Windows、およびビュー](../mfc/creating-new-documents-windows-and-views.md)です。 この記事には、重要な情報とこのテーマに関する概要情報が含まれています。

## <a name="overview"></a>概要

MFC の状態情報の 3 種類があります: モジュールの状態、プロセス、およびスレッドの状態。 場合によってこれらの状態の型を結合できます。 たとえば、MFC のハンドルのマップは、ローカル モジュールとスレッド ローカルの両方です。 これにより、そのスレッドのそれぞれに異なる複数のマップを 2 つの異なるモジュールです。

プロセスの状態とスレッドの状態は似ています。 これらのデータ項目は、グローバル変数は、広く利用されているが、特定のプロセスに固有のものか、スレッドの適切な Win32s をサポートする、または適切なマルチ スレッド サポートのある必要がある点です。 どのカテゴリ内に収まる範囲指定されたデータ項目は、そのアイテムとプロセスとスレッドの境界に関して、目的のセマンティクスに依存します。

モジュールの状態は一意に本当にグローバル状態またはローカル プロセスまたはスレッド ローカル状態のいずれかを含めることができます。 さらに、そのすばやい切り替えが可能です。

## <a name="module-state-switching"></a>モジュールの状態の切り替え

各スレッドには、モジュールの「現在」または"アクティブな"状態へのポインターが含まれています (当然ながら、MFC のスレッド ローカル状態の一部であるポインター)。 実行のスレッドが OLE コントロール、DLL、または、OLE コントロールを呼び出すアプリケーションを呼び出すアプリケーションなど、モジュール境界を通過するときに、このポインターが変更されます。

現在のモジュール状態が呼び出すことによりスイッチ`AfxSetModuleState`です。 ほとんどの場合、API を直接処理されることはありません。 MFC では、多くの場合はそれを呼び出します (WinMain、OLE のエントリ ポイントで`AfxWndProc`, などです。)。 これは、特殊な静的にリンクすることで記述する、コンポーネントに`WndProc`、および特殊な`WinMain`(または`DllMain`) するモジュールの状態を現在にする必要がありますを把握しています。 DLLMODUL を調べることで、このコードを確認できます。CPP または APPMODUL します。Mfc \src ディレクトリで CPP です。

モジュールの状態を設定し、戻されなかったことすることはまれであります。 ほとんどの場合、独自のモジュールを「プッシュ」する状態の現在の 1 つとしが完了したら、「ポップ」元のコンテキスト。 これは、マクロで[AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state)と特殊なクラス`AFX_MAINTAIN_STATE`です。

`CCmdTarget` モジュールの状態の切り替えをサポートするための特別な機能があります。 具体的には、 `CCmdTarget` OLE オートメーションおよび OLE COM のエントリ ポイントに使用されるルート クラスです。 その他の任意のエントリ ポイントと同様に、システムに公開されている、これらのエントリ ポイントは適切なモジュールの状態を設定する必要があります。 方法は、指定された`CCmdTarget`どうなるかわから「適切」のモジュールの状態が回答は、「記憶」、「現在」のモジュール状態を作成するときにに設定できるようにするには、現在のモジュール状態「記憶」その後の値と呼ばれます。 その結果、モジュールの状態を指定された`CCmdTarget`オブジェクトが関連付けられているが、オブジェクトを構築したときに現在のモジュール状態。 INPROC サーバーを読み込んで、オブジェクトを作成およびメソッドの呼び出しの簡単な例を実行します。

1.  OLE によって、DLL が読み込まれて使用`LoadLibrary`です。

2. `RawDllMain` 最初に呼び出されます。 DLL の既知の静的なモジュールの状態に、モジュールの状態に設定します。 このため`RawDllMain`DLL に静的にリンクします。

3.  このオブジェクトに関連付けられたクラス ファクトリのコンス トラクターが呼び出されます。 `COleObjectFactory` 派生した`CCmdTarget`し、その結果、どのモジュール状態でインスタンス化された記憶します。 これは重要: オブジェクトを作成するクラス ファクトリが要求されたときに認識しているようになりましたどのモジュールの状態を設定する現在します。

4. `DllGetClassObject` クラス ファクトリを取得すると呼びます。 MFC では、このモジュールに関連付けられているクラス ファクトリの一覧を検索し、それを返します。

5. `COleObjectFactory::XClassFactory2::CreateInstance` が呼ばれたとき。 オブジェクトを作成して返す、前にこの関数は手順 3. で最新だったモジュールの状態にモジュールの状態を設定 (最新だったときに 1 つ、`COleObjectFactory`がインスタンス化される)。 これは、内部の[METHOD_PROLOGUE](com-interface-entry-points.md)です。

6.  すぎますが、オブジェクトの作成時に、`CCmdTarget`派生と同じ方法で`COleObjectFactory`記憶するモジュールの状態がアクティブでもこの新しいオブジェクト。 これで、オブジェクトに切り替えるにはどのモジュールの状態を知っているたびに呼び出されます。

7.  クライアントから受信した OLE COM オブジェクトの関数を呼び出す、`CoCreateInstance`呼び出します。 使用して、オブジェクトが呼び出されたときに`METHOD_PROLOGUE`とまったく同様に、モジュールの状態を切り替えるには`COleObjectFactory`はします。

ご覧のように、モジュールの状態で作成されるオブジェクトに伝達オブジェクトからされます。 ことが重要モジュールの状態が適切に設定されています。 このオプションを設定しない場合、DLL または COM オブジェクトと連携する可能性が低い MFC アプリケーションが呼び出している、または独自のリソースを検索することがない可能性がありますまたはその他のない形で失敗する可能性があります。

特定の種類の Dll の場合、具体的には"MFC Extension"Dll がでモジュールの状態を切り替えるできませんに注意してください、 `RawDllMain` (実際には、通常も持たない、 `RawDllMain`)。 これは、場合の動作は"と"がそれらを使用するアプリケーションで実際に存在することを意図しているためにです。 これらは実行されているアプリケーションの一部では非常によくあり、その目的は、そのアプリケーションのグローバル状態を変更します。

OLE コントロールとその他の Dll が非常に異なります。 呼び出し元のアプリケーションの状態を変更しません。アプリケーションを呼び出すことができない可能性がありますも MFC アプリケーションおよびのでない可能性がありますを変更する状態。 これは、モジュールの状態の切り替えが採用する理由です。

いずれかの DLL のダイアログ ボックスを起動するなどの DLL からエクスポートされた関数の関数の先頭に次のコードを追加する必要があります。

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState())
```

モジュールの現在の状態から返された状態と交換この[AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)現在のスコープが終了するまでです。

AFX_MODULE_STATE マクロを使用しない場合は、Dll 内のリソースに問題が発生します。 既定では、MFC では、メイン アプリケーションのリソース ハンドルを使用して、リソース テンプレートを読み込みます。 このテンプレートは、DLL に実際に格納されます。 根本原因は、MFC のモジュールの状態情報が AFX_MODULE_STATE マクロが切り替えられましたいないことです。 リソース ハンドルは、MFC のモジュールの状態から回復しました。 モジュールの状態が切り替えられていないすると、間違ったリソース ハンドルが使用されます。

AFX_MODULE_STATE は、すべての関数は DLL 内に配置する必要はありません。 たとえば、 `InitInstance` MFC する前にモジュールの状態を自動的に移動するために、MFC アプリケーションのコードで AFX_MODULE_STATE せずによって呼び出されることができます`InitInstance`と後、再度スイッチ、`InitInstance`を返します。 すべてのメッセージ マップ ハンドラーの同様です。 正規の MFC Dll には、実際には、すべてのメッセージをルーティングする前にモジュールの状態は自動的に切り替わりますマスターの特殊なウィンドウ プロシージャがあり。

## <a name="process-local-data"></a>ローカル データの処理

ローカル データの処理はありません優れたこのような問題になることでなかった Win32s DLL モデルが困難なのです。 Win32s では、すべての Dll は、複数のアプリケーションによって読み込まれるときにさらに、グローバルなデータを共有します。 これは、各 DLL が各 DLL にアタッチするプロセスでそのデータ領域の個別のコピーを取得、Win32 DLL の「現実の」データ モデルで、大きく異なります。 複雑さに追加するに Win32s DLL 内のヒープに割り当てられるデータは実際には特定のプロセス (少なくとも限り所有権) です。 次のデータとコードを考えてみます。

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

起こるかどうか、上記のコード内にある DLL および DLL が A と B (ある可能性があります、実際には、同じアプリケーションの 2 つのインスタンス) の 2 つのプロセスによって読み込まれることを検討してください。 呼び出して`SetGlobalString("Hello from A")`です。 に対して割り当てられたメモリの結果として、 `CString` A. してプロセスのコンテキスト内のデータに留意する、`CString`自体はグローバルでありが両方に表示されると BB を呼び出し`GetGlobalString(sz, sizeof(sz))`です。 B は、データ セットを確認することができます。 Win32s に Win32 にはなどのプロセス間の保護では提供されないためにです。 最初の問題であります。多くの場合は、1 つのアプリケーションが別のアプリケーションが所有すると見なされるグローバル データに影響することが望ましいはありません。

その他でも問題があります。 たとえば、今すぐに終了するとします。 ときに、終了するで使用されるメモリ、'`strGlobal`' 文字列は、システムの使用可能になります: オペレーティング システムがプロセスによって割り当てられたすべてのメモリを自動的に解放はつまり、します。 は解放されず、`CString`デストラクターが呼び出されている以外の場合はまだ呼び出されていません。 単純に解放されるため、割り当てられているアプリケーションが終了します。 ここで B `GetGlobalString(sz, sizeof(sz))`、有効なデータはならない場合があります。 他のアプリケーションが、何か他のメモリを使用している可能性がありますがします。

明確に問題が存在します。 MFC 3.x がスレッド ローカル ストレージ (TLS) と呼ばれる手法を使用します。 MFC 3.x は呼び出されませんいるにもかかわらず、win32s 本当にプロセス ローカル ストレージのインデックスとして機能する TLS インデックスを割り当てるし、し、その TLS インデックスに基づくすべてのデータを参照します。 これは Win32 上のスレッド ローカル データの格納に使用された TLS インデックスに似ています (そのサブジェクトの詳細については、下記参照)。 これにより、プロセスごとに少なくとも 2 つの TLS インデックスを利用するすべての MFC DLL が原因です。 多く OLE コントロールの Dll (Ocx) の読み込みを考慮するときにすぐに不足する TLS インデックス (が 64 のみ使用できます)。 さらに、MFC では、このデータはすべてを 1 つの構造内の 1 つの場所に配置する必要があります。 非常に拡張できませんでしたし、TLS インデックスの使用に関して最適でした。

MFC を「ラップ」プロセスがローカルにする必要のあるデータに関連するクラス テンプレートのセットにこの 4.x に対処します。 たとえば、上の問題を記述して修復可能性があります。

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

MFC では、2 つの手順でこれを実装します。 最初に、Win32 の上位層がある__Tls\*__  Api (**TlsAlloc**、 **TlsSetValue**、 **TlsGetValue**など) を必要がある Dll の数に関係なく、プロセスごとの 2 つだけの TLS インデックスを使用します。 2 番目、`CProcessLocal`テンプレートはこのデータにアクセスを提供します。 演算子をオーバーライド -> 新機能により、直感的な構文上を参照してください。 すべてのオブジェクトによってラップされている`CProcessLocal`から派生する必要があります`CNoTrackObject`です。 `CNoTrackObject` 下位レベルのアロケーターは、(**LocalAlloc**/**LocalFree**) および仮想デストラクターにプロセスが終了した場合に、MFC はプロセスのローカル オブジェクトを破棄自動的にできます。 このようなオブジェクトは、その他のクリーンアップが必要な場合、カスタム デストラクターを持つことができます。 上の例では、コンパイラは、埋め込みを破棄する既定のデストラクターを生成するため`CString`オブジェクト。

このアプローチには他の興味深い長所があります。 いるだけでなく、すべて`CProcessLocal`オブジェクトが自動的に破棄される必要になるまで構築されません。 `CProcessLocal::operator->` 初めて呼び出されると、関連付けられたオブジェクトおよびありません早くをインスタンス化されます。 したがって、上記の例では、'`strGlobal`' 文字列は、初めてまで作成されません`SetGlobalString`または`GetGlobalString`と呼びます。 場合によっては、DLL の開始時間を短縮これのに役立ちます。

## <a name="thread-local-data"></a>スレッド ローカル データ

ローカル データの処理と同様に、スレッド ローカル データは場合に使用データは、特定のスレッドのローカルである必要があります。 つまり、そのデータにアクセスする各スレッドのデータの個別のインスタンスが必要です。 これは、何度も使用できますの広範な同期機構を使用せずにします。 データが複数のスレッドで共有する必要がない場合、このようなメカニズムは、高価で不要なに指定できます。 発生しました。 たとえば、 `CString` (非常によく似た上記のサンプル) オブジェクト。 スレッドのローカルでラップすることによって、`CThreadLocal`テンプレート。

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

場合`MakeRandomString`が呼び出された 2 つの異なるスレッドから各は「シャッフル」文字列さまざまな方法で、他を妨げることがなくです。 これが実際には、`strThread`グローバル インスタンスを 1 つだけではなく、スレッドごとのインスタンス。

キャプチャする参照を使用する方法に注意してください、`CString`アドレス 1 回の代わりに 1 回のループ反復ごとです。 ループのコードを記述と`threadData->strThread`everywhere '`str`' を使用するが、コードは実行速度が著しく低下します。 ループ内でこのような参照が発生したときに、データへの参照をキャッシュすることをお勧めします。

`CThreadLocal`クラス テンプレートと同じメカニズムを使用している`CProcessLocal`働きと実装のと同じ手法です。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)  
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)  
