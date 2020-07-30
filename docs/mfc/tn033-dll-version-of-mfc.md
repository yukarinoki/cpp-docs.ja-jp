---
title: 'テクニカル ノート 33: MFC の DLL バージョン'
ms.date: 06/28/2018
helpviewer_keywords:
- MFC DLLs [MFC], writing MFC extension DLLS
- AFXDLL library
- DLLs [MFC], MFC
- DLL version of MFC [MFC]
- TN033
ms.assetid: b6f1080b-b66b-4b1e-8fb1-926c5816392c
ms.openlocfilehash: c627f891efc893f4eb8dae4bfb0b3b78f7af1a46
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215934"
---
# <a name="tn033-dll-version-of-mfc"></a>テクニカル ノート 33: MFC の DLL バージョン

このメモでは、MFC アプリケーションと MFC 拡張 Dll を使用して、MFCxx.DLL と MFCxxD.DLL (x は MFC バージョン番号) 共有ダイナミックリンクライブラリを使用する方法について説明します。 通常の MFC Dll の詳細については、「 [DLL の一部としての mfc の使用](../mfc/tn011-using-mfc-as-part-of-a-dll.md)」を参照してください。

このテクニカルノートでは、Dll の3つの側面について説明します。 最後の2つは、より高度なユーザー向けです。

- [MFC 拡張 DLL のビルド方法](#_mfcnotes_how_to_write_an_mfc_extension_dll)

- [MFC の DLL バージョンを使用する MFC アプリケーションのビルド方法](#_mfcnotes_writing_an_application_that_uses_the_dll_version)

- [MFC 共有ダイナミックリンクライブラリの実装方法](#_mfcnotes_how_the_mfc30.dll_is_implemented)

Mfc を使用して、MFC 以外のアプリケーション (これは通常の MFC DLL と呼ばれます) で使用できる DLL をビルドする場合は、[テクニカルノート 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md)を参照してください。

## <a name="overview-of-mfcxxdll-support-terminology-and-files"></a>MFCxx.DLL サポートの概要: 用語とファイル

**レギュラー MFC dll**: mfc の一部のクラスを使用して、スタンドアロン dll を構築するには、通常の mfc dll を使用します。 アプリケーション/DLL の境界を越えたインターフェイスは "C" インターフェイスであり、クライアントアプリケーションは MFC アプリケーションである必要はありません。

これは、MFC 1.0 でサポートされている DLL サポートのバージョンです。 詳細については、「[テクニカルノート 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md) 」と「MFC の高度な概念のサンプル[DLLScreenCap](../overview/visual-cpp-samples.md)」を参照してください。

> [!NOTE]
> Visual C++ バージョン4.0 では、 **USRDLL**という用語は互換性のために残されており、mfc と静的にリンクする通常の mfc DLL に置き換えられています。 MFC と動的にリンクするレギュラー MFC DLL をビルドすることもできます。

MFC 3.0 (およびそれ以降) では、OLE クラスとデータベースクラスを含む、すべての新機能を備えた通常の MFC Dll がサポートされています。

**AFXDLL**: これは、MFC ライブラリの共有バージョンとも呼ばれます。 これは、MFC 2.0 で追加された新しい DLL サポートです。 MFC ライブラリ自体は多数の Dll (以下で説明) に含まれており、クライアントアプリケーションまたは DLL は、必要な Dll を動的にリンクします。 アプリケーション/DLL の境界を越えたインターフェイスは、C++/MFC クラスのインターフェイスです。 クライアントアプリケーションは、MFC アプリケーションである必要があります。 MFC 3.0 のすべての機能をサポートしています (例外: UNICODE はデータベースクラスではサポートされていません)。

> [!NOTE]
> Visual C++ バージョン4.0 では、このタイプの DLL は "拡張 DLL" と呼ばれます。

このメモでは、MFCxx.DLL を使用して MFC DLL セット全体を参照します。これには次のものが含まれます。

- デバッグ: MFCxxD.DLL (結合) と MFCSxxD .LIB (static)。

- リリース: MFCxx.DLL (結合) と MFCSxx .LIB (静的)。

- Unicode デバッグ: MFCxxUD.DLL (結合) と MFCSxxD .LIB (static)。

- Unicode リリース: MFCxxU.DLL (結合) と MFCSxxU .LIB (static)。

> [!NOTE]
> MFCSxx [U] [D]。LIB ライブラリは、MFC の共有 Dll と共に使用されます。 これらのライブラリには、アプリケーションまたは DLL に静的にリンクする必要があるコードが含まれています。

アプリケーションは、対応するインポートライブラリにリンクします。

- デバッグ: MFCxxD .LIB

- リリース: Mfcxx.dll

- Unicode デバッグ: MFCxxUD

- Unicode リリース: MFCxxU .LIB

"MFC 拡張 DLL" は、MFCxx.DLL (またはその他の MFC 共有 Dll) に基づいて構築された DLL です。 ここでは、MFC コンポーネントアーキテクチャを開始します。 MFC クラスから有用なクラスを派生させたり、別の MFC に似たツールキットをビルドしたりする場合は、DLL に配置できます。 この DLL は、ultimate クライアントアプリケーションと同様に、MFCxx.DLL を使用します。 これにより、再利用可能なリーフクラス、再利用可能な基底クラス、および再利用可能なビュー/ドキュメントクラスが許可されます。

## <a name="pros-and-cons"></a>長所と短所

MFC の共有バージョンを使用する理由

- 共有ライブラリを使用すると、アプリケーションのサイズが小さくなる可能性があります (ほとんどの MFC ライブラリを使用する最小限のアプリケーションは、10K 未満)。

- MFC の共有バージョンでは、MFC 拡張 Dll と通常の MFC Dll がサポートされています。

- Mfc 自体をリンクする必要がないため、共有 MFC ライブラリを使用するアプリケーションをビルドする方が、静的にリンクされた MFC アプリケーションを作成するよりも高速です。 これは、デバッグ情報を圧縮する必要がある**デバッグ**ビルドで特に当てはまります。デバッグ情報が既に含まれている DLL とリンクすることで、アプリケーション内でコンパクトにするデバッグ情報が少なくなります。

MFC の共有バージョンを使用しないのはなぜですか。

- 共有ライブラリを使用するアプリケーションを配布するには、MFCxx.DLL (およびその他) のライブラリをプログラムと一緒に発送する必要があります。 MFCxx.DLL は多くの Dll のように自由に再配布できますが、セットアッププログラムに DLL をインストールする必要があります。 また、プログラムと MFC Dll の両方で使用される C ランタイムライブラリを含む MSVCRTxx.DLL を出荷する必要があります。

## <a name="how-to-write-an-mfc-extension-dll"></a><a name="_mfcnotes_how_to_write_an_mfc_extension_dll"></a>方法: MFC 拡張 DLL を記述する

MFC 拡張 DLL は、MFC クラスの機能を embellish するために記述されたクラスと関数を含む DLL です。 MFC 拡張 DLL は、アプリケーションが使用するのと同じ方法で共有 MFC Dll を使用します。追加の考慮事項がいくつかあります。

- ビルドプロセスは、共有 MFC ライブラリを使用するアプリケーションをビルドする場合と似ていますが、いくつかの追加のコンパイラオプションとリンカーオプションがあります。

- MFC 拡張 DLL には、の派生クラスがありません `CWinApp` 。

- MFC 拡張 DLL では、特別なを提供する必要があり `DllMain` ます。 AppWizard には、変更可能な関数が用意さ `DllMain` れています。

- Mfc 拡張 dll は、通常、 `CDynLinkLibrary` mfc 拡張 dll が `CRuntimeClass` アプリケーションに es またはリソースをエクスポートする場合に、を作成するための初期化ルーチンを提供します。 `CDynLinkLibrary`アプリケーションごとのデータを MFC 拡張 DLL で維持する必要がある場合は、の派生クラスを使用できます。

これらの考慮事項については、以下で詳しく説明します。 次に示すように、MFC の高度な概念のサンプル[DLLHUSK](../overview/visual-cpp-samples.md)も参照してください。

- 共有ライブラリを使用したアプリケーションの構築。 (DLLHUSK.EXE は、mfc ライブラリおよびその他の Dll と動的にリンクする MFC アプリケーションです)。

- MFC 拡張 DLL のビルド。 ( `_AFXEXT` MFC 拡張 DLL のビルドで使用されるなどの特殊なフラグに注意してください)

- MFC 拡張 Dll の2つの例。 1つは、制限付きエクスポート (TESTDLL1) を使用した MFC 拡張 DLL の基本構造を示し、もう1つはクラスインターフェイス全体 (TESTDLL2) をエクスポートする方法を示しています。

クライアントアプリケーションと MFC 拡張 Dll の両方で、同じバージョンの MFCxx.DLL を使用する必要があります。 MFC DLL の規則に従い、MFC 拡張 DLL の debug と retail (/release) バージョンの両方を提供する必要があります。 これにより、クライアントプログラムは、アプリケーションのデバッグバージョンと製品版の両方をビルドし、すべての Dll の適切なデバッグバージョンまたは製品版にリンクできます。

> [!NOTE]
> C++ の名前の変形とエクスポートの問題のため、MFC 拡張 DLL からのエクスポートリストは、同じ DLL のデバッグバージョンと製品版とで異なる場合があります。 小売 MFCxx.DLL には、約2000のエントリポイントがエクスポートされています。デバッグ MFCxxD.DLL には、約3000のエントリポイントがエクスポートされています。

### <a name="quick-note-on-memory-management"></a>メモリ管理に関するクイックメモ

このテクニカルノートの最後にある「メモリ管理」というタイトルのセクションでは、MFC の共有バージョンでの MFCxx.DLL の実装について説明しています。 MFC 拡張 DLL だけを実装するために必要な情報については、ここで説明します。

MFCxx.DLL と、クライアントアプリケーションのアドレス空間に読み込まれたすべての MFC 拡張 Dll は、同じアプリケーション内にあるかのように、同じメモリアロケーター、リソース読み込み、およびその他の MFC の "グローバル" 状態を使用します。 これが重要なのは、mfc に静的にリンクする非 MFC DLL ライブラリと通常の MFC Dll が厳密に逆の処理を実行し、各 DLL が独自のメモリプールから割り当てられるためです。

MFC 拡張 DLL がメモリを割り当てると、そのメモリは他のアプリケーションで割り当てられたオブジェクトと自由に混在させることができます。 また、共有 MFC ライブラリを使用するアプリケーションがクラッシュした場合、オペレーティングシステムの保護によって、DLL を共有する他の MFC アプリケーションの整合性が維持されます。

同様に、リソースを読み込むための現在の実行可能ファイルと同様に、他の "グローバル" MFC の状態も、クライアントアプリケーションとすべての MFC 拡張 Dll の間で共有され、MFCxx.DLL 自体も共有されます。

### <a name="building-an-mfc-extension-dll"></a>MFC 拡張 DLL のビルド

AppWizard を使用して MFC 拡張 DLL プロジェクトを作成すると、適切なコンパイラとリンカーの設定が自動的に生成されます。 また、変更できる関数も生成されました `DllMain` 。

既存のプロジェクトを MFC 拡張 DLL に変換する場合は、まず、MFC の共有バージョンを使用してアプリケーションをビルドするための標準の規則を使用し、次の手順を実行します。

- コンパイラフラグに追加 **/D_AFXEXT**します。 [プロジェクトのプロパティ] ダイアログボックスで、[C/c + +] ノードを選択します。 次に、[プリプロセッサ] カテゴリを選択します。 [ `_AFXEXT` マクロの定義] フィールドにを追加して、各項目をセミコロンで区切ります。

- **/Gy**コンパイラスイッチを削除します。 [プロジェクトのプロパティ] ダイアログボックスで、[C/c + +] ノードを選択します。 次に、[コード生成] カテゴリを選択します。 [関数レベルのリンクを有効にする] オプションが有効になっていないことを確認します。 これにより、リンカーは参照されていない関数を削除しないため、クラスのエクスポートが容易になります。 元のプロジェクトを使用して MFC に静的にリンクされたレギュラー MFC DLL をビルドする場合は、 **/mt [d]** コンパイラオプションを **/md [d]** に変更します。

- リンクする **/dll**オプションを使用して、エクスポートライブラリをビルドします。 これは、Win32 ダイナミックリンクライブラリをターゲットの種類として指定して、新しいターゲットを作成するときに設定されます。

### <a name="changing-your-header-files"></a>ヘッダーファイルの変更

MFC 拡張 DLL の目的は通常、その機能を使用できる1つ以上のアプリケーションにいくつかの一般的な機能をエクスポートすることです。 これは、クライアントアプリケーションで使用できるクラスおよびグローバル関数のエクスポートについて要約しています。

このためには、各メンバー関数がインポートまたはエクスポートとして適切にマークされていることを確認する必要があります。 これには、との特別な宣言が必要です `__declspec(dllexport)` `__declspec(dllimport)` 。 クラスがクライアントアプリケーションによって使用される場合は、として宣言する必要が `__declspec(dllimport)` あります。 MFC 拡張 DLL 自体をビルドする場合は、として宣言する必要があり `__declspec(dllexport)` ます。 また、これらの関数は、クライアントプログラムが読み込み時にそれらにバインドされるように、実際にエクスポートする必要があります。

クラス全体をエクスポートするには、 `AFX_EXT_CLASS` クラス定義でを使用します。 このマクロは、とが定義されている場合と同様にフレームワークによって定義され `__declspec(dllexport)` `_AFXDLL` ますが、が定義されて `_AFXEXT` いない場合として定義され `__declspec(dllimport)` `_AFXEXT` ます。 `_AFXEXT`前述のように、は、MFC 拡張 DLL をビルドするときにのみ定義されます。 次に例を示します。

```cpp
class AFX_EXT_CLASS CExampleExport : public CObject
{ /* ... class definition ... */ };
```

### <a name="not-exporting-the-entire-class"></a>クラス全体をエクスポートしない

場合によっては、クラスに必要な個々のメンバーだけをエクスポートする必要があります。 たとえば、`CDialog` 派生クラスをエクスポートする場合に、コンストラクターと `DoModal` 呼び出しのエクスポートだけが必要な場合があります。 これらのメンバーは、DLL のを使用してエクスポートできます。DEF ファイルを使用することもでき `AFX_EXT_CLASS` ますが、エクスポートに必要な個々のメンバーに対してもほぼ同じ方法でを使用できます。

次に例を示します。

```cpp
class CExampleDialog : public CDialog
{
public:
    AFX_EXT_CLASS CExampleDialog();
    AFX_EXT_CLASS int DoModal();
    // rest of class definition
    // ...
};
```

この場合、クラスのすべてのメンバーをエクスポートしなくなったため、追加の問題が発生する可能性があります。 この問題は、MFC マクロの動作方法にあります。 MFC のヘルパー マクロのいくつかは、実際にデータ メンバーを宣言または定義します。 そのため、これらのデータメンバーは、DLL からエクスポートする必要もあります。

たとえば、MFC 拡張 DLL をビルドするときに、DECLARE_DYNAMIC マクロは次のように定義されます。

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
    static CRuntimeClass* PASCAL _GetBaseClass(); \
    public: \
    static AFX_DATA CRuntimeClass class##class_name; \
    virtual CRuntimeClass* GetRuntimeClass() const; \
```

"Static" を開始する行 `AFX_DATA` は、クラス内の静的オブジェクトを宣言しています。 このクラスを正しくエクスポートし、クライアントからランタイム情報にアクセスする場合は。EXE。この静的オブジェクトをエクスポートする必要があります。 静的オブジェクトは修飾子 `AFX_DATA` を使用して宣言されているため、DLL をビルドするときには `AFX_DATA` が `__declspec(dllexport)` になるように定義し、クライアント実行可能ファイルをビルドするときには `__declspec(dllimport)` として定義するだけで済みます。

前に説明したように、 `AFX_EXT_CLASS` は既にこの方法で定義されています。 `AFX_DATA`クラス定義の場合と同じになるように、再定義する必要があり `AFX_EXT_CLASS` ます。

次に例を示します。

```cpp
#undef  AFX_DATA
#define AFX_DATA AFX_EXT_CLASS
class CExampleView : public CView
{
    DECLARE_DYNAMIC()
    // ... class definition ...
};
#undef  AFX_DATA
#define AFX_DATA
```

MFC では、 `AFX_DATA` マクロ内で定義されているデータ項目に対して常にシンボルが使用されるため、この手法はすべてのシナリオで機能します。 たとえば、DECLARE_MESSAGE_MAP に対して機能します。

> [!NOTE]
> クラスの選択したメンバーではなくクラス全体をエクスポートする場合は、静的データ メンバーは自動的にエクスポートされます。

同じ手法を使用して、 `CArchive` DECLARE_SERIAL および IMPLEMENT_SERIAL マクロを使用するクラスの抽出演算子を自動的にエクスポートできます。 にあるクラス宣言を角かっこで、archive 演算子をエクスポートします。H ファイル) を次のコードに置き換えます。

```cpp
#undef AFX_API
#define AFX_API AFX_EXT_CLASS

/* your class declarations here */

#undef AFX_API
#define AFX_API
```

### <a name="limitations-of-_afxext"></a>_AFXEXT の制限事項

Mfc 拡張 dll の複数のレイヤーがない場合は、MFC 拡張 Dll の _**afxext.h**プリプロセッサシンボルを使用できます。 MFC クラスから派生する独自の MFC 拡張 DLL のクラスがあり、そこから呼び出すか派生する MFC 拡張 DLL がある場合は、あいまいさを避けるために独自のプリプロセッサ シンボルを使用する必要があります。

この問題が発生するのは、Win32 では、データを DLL からエクスポートする場合と同じように明示的に宣言する必要があり、 `__declspec(dllexport)` `__declspec(dllimport)` dll からインポートする場合です。 を定義する場合 `_AFXEXT` 、MFC ヘッダーは `AFX_EXT_CLASS` が正しく定義されていることを確認します。

複数のレイヤーがある場合は、などの1つのシンボル `AFX_EXT_CLASS` が不足しています。これは、mfc 拡張 dll が新しいクラスをエクスポートしたり、別の mfc 拡張 dll から他のクラスをインポートしたりする可能性があるためです。 この問題に対処するには、dll 自体をビルドしていること、および DLL を使用していることを示す特別なプリプロセッサシンボルを使用します。 たとえば、2つの MFC 拡張 Dll、A.DLL、および B.DLL を考えてみます。 各クラスは、それぞれ .H と B .H のクラスをそれぞれエクスポートします。 B.DLL は A.DLL のクラスを使用します。 ヘッダー ファイルは次のようになります。

```cpp
/* A.H */
#ifdef A_IMPL
    #define CLASS_DECL_A   __declspec(dllexport)
#else
    #define CLASS_DECL_A   __declspec(dllimport)
#endif

class CLASS_DECL_A CExampleA : public CObject
{ /* ... class definition ... */ };

/* B.H */
#ifdef B_IMPL
    #define CLASS_DECL_B   __declspec(dllexport)
#else
    #define CLASS_DECL_B   __declspec(dllimport)
#endif

class CLASS_DECL_B CExampleB : public CExampleA
{ /* ... class definition ... */ };
```

A.DLL が構築されると、 **/DA_IMPL**でビルドされ、B.DLL が構築されると、 **/DB_IMPL**でビルドされます。 DLL ごとに個別のシンボルを使用することにより、CCExampleA がエクスポートされ、B.DLL のビルド時にインポートされます。 CExampleA は、B.DLL (またはその他のクライアント) によって使用された場合に、A.DLL を作成してインポートするときにエクスポートされます。

組み込み `AFX_EXT_CLASS` `_AFXEXT` シンボルおよびプリプロセッサシンボルを使用する場合、この種のレイヤーは実行できません。 上記の手法では、OLE、データベース、および Network MFC 拡張 Dll を構築するときに MFC 自体が使用する機構とは異なり、この問題を解決します。

### <a name="not-exporting-the-entire-class"></a>クラス全体をエクスポートしない

ここでも、クラス全体をエクスポートしない場合は、特別な注意が必要です。 MFC マクロによって作成された必要なデータ項目が正しくエクスポートされていることを確認する必要があります。 これは `AFX_DATA` 、特定のクラスのマクロに再定義することによって行うことができます。 クラス全体をエクスポートしない場合は、この処理を常に実行することをお勧めします。

次に例を示します。

```cpp
// A.H
#ifdef A_IMPL
    #define CLASS_DECL_A  _declspec(dllexport)
#else
    #define CLASS_DECL_A  _declspec(dllimport)
#endif

#undef  AFX_DATA
#define AFX_DATA CLASS_DECL_A

class CExampleA : public CObject
{
    DECLARE_DYNAMIC()
    CLASS_DECL_A int SomeFunction();
    // class definition
    // ...
};

#undef AFX_DATA
#define AFX_DATA
```

### <a name="dllmain"></a>DllMain

次に示すのは、MFC 拡張 DLL のメインソースファイルに配置する必要がある正確なコードです。 これは、標準のに含まれています。 AppWizard を使用して MFC 拡張 DLL のスターターファイルを作成すると、が提供されることに注意して `DllMain` ください。

```cpp
#include "afxdllx.h"

static AFX_EXTENSION_MODULE extensionDLL;

extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID)
{
   if (dwReason == DLL_PROCESS_ATTACH)
   {
      // MFC extension DLL one-time initialization
      if (!AfxInitExtensionModule(
             extensionDLL, hInstance))
         return 0;

      // TODO: perform other initialization tasks here
   }
   else if (dwReason == DLL_PROCESS_DETACH)
   {
      // MFC extension DLL per-process termination
      AfxTermExtensionModule(extensionDLL);

      // TODO: perform other cleanup tasks here
   }
   return 1;   // ok
}
```

への呼び出しは、 `AfxInitExtensionModule` オブジェクトの作成時に後で使用するために、モジュールのランタイムクラス ( `CRuntimeClass` 構造体) およびオブジェクトファクトリ (オブジェクト) をキャプチャし `COleObjectFactory` `CDynLinkLibrary` ます。 (省略可能) の呼び出しに `AfxTermExtensionModule` より、各プロセスがデタッチされたとき (プロセスが終了したとき、または dll が呼び出しの結果としてアンロードされたとき) に mfc 拡張 dll をクリーンアップでき `FreeLibrary` ます。 ほとんどの MFC 拡張 Dll は動的に読み込まれない (通常はインポートライブラリを介してリンクされる) ため、の呼び出し `AfxTermExtensionModule` は通常必要ありません。

アプリケーションで MFC 拡張 Dll を動的に読み込んで解放する場合は、上記のように、を必ず呼び出し `AfxTermExtensionModule` てください。 また `AfxLoadLibrary` 、 `AfxFreeLibrary` `LoadLibrary` `FreeLibrary` アプリケーションで複数のスレッドを使用する場合、または MFC 拡張 DLL を動的に読み込む場合は、(Win32 関数およびではなく) とを使用してください。 およびを使用する `AfxLoadLibrary` と、 `AfxFreeLibrary` MFC 拡張 DLL が読み込まれてアンロードされるときに実行される起動コードとシャットダウンコードが、mfc のグローバル状態を破壊しないことが保証されます。

ヘッダーファイル AFXDLLX。H には、およびの定義など、MFC 拡張 Dll で使用される構造体の特別な定義が含まれてい `AFX_EXTENSION_MODULE` `CDynLinkLibrary` ます。

グローバル*Extensiondll*は、示されているように宣言する必要があります。 16ビットバージョンの MFC とは異なり、この時点ではメモリを割り当て、MFC 関数を呼び出すことができます。これは、の呼び出し時に MFCxx.DLL が完全に初期化されるためです `DllMain` 。

### <a name="sharing-resources-and-classes"></a>リソースやクラスの共有

単純な MFC 拡張 Dll では、クライアントアプリケーションに少数の低帯域幅の関数をエクスポートするだけで済みます。 ユーザーインターフェイスを多用する Dll の多くは、リソースと C++ クラスをクライアントアプリケーションにエクスポートすることが必要になる場合があります。

リソースのエクスポートには、リソース リストを使います。 各アプリケーションは、オブジェクトの単一のリンクリストです `CDynLinkLibrary` 。 リソースを検索する場合、リソースを読み込む標準的な MFC 実装のほとんどは、まず現在のリソースモジュール ( `AfxGetResourceHandle` ) を参照し、見つからない場合は、要求されたリソースを読み込もうとしているオブジェクトの一覧を確認し `CDynLinkLibrary` ます。

C++ クラス名が指定された C++ オブジェクトの動的作成も同様です。 MFC オブジェクトの逆シリアル化機構には、前に格納され `CRuntimeClass` た内容に基づいて、必要な型の C++ オブジェクトを動的に作成することによって再構築できるように、すべてのオブジェクトが登録されている必要があります。

クライアントアプリケーションで MFC 拡張 DLL のクラスを使用する場合は `DECLARE_SERIAL` 、クライアントアプリケーションに表示されるようにクラスをエクスポートする必要があります。 これは、リストを調べても実行され `CDynLinkLibrary` ます。

MFC の高度な概念のサンプル[DLLHUSK](../overview/visual-cpp-samples.md)の場合、一覧は次のようになります。

```Example
head ->   DLLHUSK.EXE   - or - DLLHUSK.EXE
               |                    |
          TESTDLL2.DLL         TESTDLL2.DLL
               |                    |
          TESTDLL1.DLL         TESTDLL1.DLL
               |                    |
               |                    |
           MFC90D.DLL           MFC90.DLL
```

通常、MFCxx.DLL はリソースとクラスの一覧に最後にあります。 MFCxx.DLL には、すべての標準コマンド Id のプロンプト文字列を含む、すべての標準 MFC リソースが含まれています。 これをリストの末尾に配置すると、Dll とクライアントアプリケーション自体が標準 MFC リソースの独自のコピーを持つことができなくなります。ただし、代わりに MFCxx.DLL 内の共有リソースに依存することになります。

すべての Dll のリソースとクラス名をクライアントアプリケーションの名前空間にマージすると、選択した Id または名前に注意する必要があるという欠点があります。 もちろん、この機能を無効にするには、リソースまたはオブジェクトをクライアントアプリケーションにエクスポートしないようにし `CDynLinkLibrary` ます。 [DLLHUSK](../overview/visual-cpp-samples.md) サンプルでは、複数のヘッダー ファイルを使って、共有リソースの名前空間を管理します。 共有リソースファイルの使用に関するその他のヒントについては、「[テクニカルノート 35](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md) 」を参照してください。

### <a name="initializing-the-dll"></a>DLL の初期化

前述のように、通常は、 `CDynLinkLibrary` リソースとクラスをクライアントアプリケーションにエクスポートするために、オブジェクトを作成します。 DLL を初期化するには、エクスポートされたエントリポイントを指定する必要があります。 最小値は、引数を取らず、何も返さない void ルーチンですが、任意のものを指定できます。

この方法を使用する場合は、DLL を使用する各クライアントアプリケーションが、この初期化ルーチンを呼び出す必要があります。 を呼び出した直後に、このオブジェクトをに割り当てることもでき `CDynLinkLibrary` `DllMain` `AfxInitExtensionModule` ます。

初期化ルーチンは、現在の `CDynLinkLibrary` アプリケーションのヒープにオブジェクトを作成する必要があります。このとき、MFC 拡張 DLL 情報に接続します。 これは、次の方法で行うことができます。

```cpp
extern "C" extern void WINAPI InitXxxDLL()
{
    new CDynLinkLibrary(extensionDLL);
}
```

この例の一般的な名前である*Initxxx dll*は、任意のものにすることができます。 **Extern "C"** である必要はありませんが、これを行うと、エクスポートリストが管理しやすくなります。

> [!NOTE]
> 通常の MFC DLL から MFC 拡張 DLL を使用する場合は、この初期化関数をエクスポートする必要があります。 MFC 拡張 DLL クラスまたはリソースを使用する前に、通常の MFC DLL からこの関数を呼び出す必要があります。

### <a name="exporting-entries"></a>エクスポート (エントリを)

クラスをエクスポートする簡単な方法は、 `__declspec(dllimport)` `__declspec(dllexport)` エクスポートする各クラスおよびグローバル関数でおよびを使用することです。 これにより、エクスポートされる関数をより細かく制御でき、序数によって関数をエクスポートできなくなるため、各エントリポイントに名前を付けるよりもはるかに簡単になります。 TESTDLL1 と TESTDLL2 は、このメソッドを使用してエントリをエクスポートします。

より効率的なメソッド (および MFCxx.DLL で使用されるメソッド) は、の各エントリに名前を付けて、各エントリを手動でエクスポートします。DEF ファイル。 ここでは、DLL から選択的エクスポートをエクスポートするため (すべてではありません)、エクスポートする特定のインターフェイスを決定する必要があります。 では、破損した名前をのエントリの形式でリンカーに指定する必要があるため、これは困難です。DEF ファイル。 C++ クラスのシンボリックリンクが本当に必要でない限り、エクスポートしないでください。

を使用して C++ クラスをエクスポートしようとした場合。DEF ファイル以前は、このリストを自動的に生成するツールを開発することができます。 これは、2段階のリンクプロセスを使用して行うことができます。 DLL をエクスポートせずに1回リンクし、リンカーでを生成できるようにします。マップファイル。 、.マップファイルを使用すると、エクスポートする必要がある関数の一覧を生成できます。そのため、一部の再配置では、のエクスポートエントリを生成するために使用できます。DEF ファイル。 このようなプロセスでは、MFCxx.DLL および OLE およびデータベース MFC 拡張 Dll のエクスポート一覧 (数千単位) が生成されましたが、このようなプロセスで生成されています (ただし、完全には自動ではなく、しばらくの間に1回、手動でチューニングする必要があります)。

### <a name="cwinapp-vs-cdynlinklibrary"></a>CWinApp と CDynLinkLibrary

MFC 拡張 DLL には、 `CWinApp` 独自のの派生オブジェクトはありません。代わりに、 `CWinApp` クライアントアプリケーションのから派生したオブジェクトを使用する必要があります。 これは、クライアントアプリケーションがメインメッセージポンプ、アイドルループなどを所有していることを意味します。

MFC 拡張 DLL で、アプリケーションごとに追加のデータを保持する必要がある場合は、から新しいクラスを派生させ、 `CDynLinkLibrary` 上記の Initxxx dll ルーチンで作成することができます。 DLL を実行すると、現在のアプリケーションのオブジェクトの一覧をチェックして、 `CDynLinkLibrary` その特定の MFC 拡張 DLL のオブジェクトを見つけることができます。

### <a name="using-resources-in-your-dll-implementation"></a>DLL 実装でのリソースの使用

前述のように、既定のリソースの読み込みでは、 `CDynLinkLibrary` 要求されたリソースを持つ最初の EXE または DLL を検索するオブジェクトの一覧が表示されます。 すべての MFC Api とすべての内部コードで、リソースリストを使用してリソースの `AfxFindResourceHandle` 一覧を調べ、リソースがどこに存在する場合でも検索することができます。

特定の場所からのみリソースを読み込む場合は、Api およびを使用して、 `AfxGetResourceHandle` `AfxSetResourceHandle` 古いハンドルを保存し、新しいハンドルを設定します。 クライアント アプリケーションに戻る前に、元のリソース ハンドルを必ず復元してください。 このサンプル TESTDLL2 では、この方法を使用してメニューを明示的に読み込みます。

リストを検索する場合、多少速度が低下することとリソース ID 範囲の管理が必要なことが欠点です。 いくつかの MFC 拡張 DLL にリンクされるクライアント アプリケーション側で、DLL のインスタンス ハンドルを指定しなくても、DLL が提供する任意のリソースを使用できるという利点もあります。 `AfxFindResourceHandle` は、リソース リストを検索して一致するリソースを見つけるのに使われる API です。 リソースの名前と型を受け取り、最初に一致したリソース ハンドル (または NULL) を返します。

## <a name="writing-an-application-that-uses-the-dll-version"></a><a name="_mfcnotes_writing_an_application_that_uses_the_dll_version"></a>DLL バージョンを使用するアプリケーションの作成

### <a name="application-requirements"></a>アプリケーションの要件

MFC の共有バージョンを使用するアプリケーションは、次のいくつかの簡単な規則に従う必要があります。

- これには、オブジェクトがあり、 `CWinApp` メッセージポンプの標準規則に従う必要があります。

- このメソッドは、必要なコンパイラフラグのセット (下記参照) を使用してコンパイルする必要があります。

- これは、Mfcxx.dll インポートライブラリとリンクする必要があります。 必要なコンパイラフラグを設定することにより、MFC ヘッダーは、アプリケーションをリンクする必要があるライブラリをリンク時に決定します。

- 実行可能ファイルを実行するには、MFCxx.DLL パスまたは Windows システムディレクトリに存在する必要があります。

### <a name="building-with-the-development-environment"></a>開発環境でのビルド

ほとんどの標準既定値で内部メイクファイルを使用している場合は、プロジェクトを簡単に変更して DLL バージョンをビルドできます。

次の手順は、NAFXCWD.LIB」にリンクされている MFC アプリケーションが正しく機能していることを前提としています。LIB (デバッグ用) と NAFXCW。LIB (リテール版) で、MFC ライブラリの共有バージョンを使用するように変換します。 Visual C++ 環境を実行していて、内部プロジェクトファイルを持っている。

1. [**プロジェクト**] メニューの [**プロパティ**] をクリックします。 [**全般**] ページの [**プロジェクトの既定値**] で、共有 DLL (mfcxx.dll (d) .dll)**で MFC を使用**するように Microsoft Foundation Classes を設定します。

### <a name="building-with-nmake"></a>ビルド (NMAKE を使用して)

Visual C++ の外部メイクファイル機能を使用している場合、または NMAKE を直接使用している場合は、コンパイラとリンカーのオプションをサポートするためにメイクファイルを編集する必要があります。

必要なコンパイラフラグ:

- **/D_AFXDLL/MD** 
   **/D_AFXDLL**

標準の MFC ヘッダーには、このシンボルを定義する必要があります。

- **/Md**アプリケーションでは、C ランタイムライブラリの DLL バージョンを使用する必要があります。

他のすべてのコンパイラフラグは、MFC の既定値に従います (たとえば、デバッグの場合は _DEBUG)。

ライブラリのリンカーリストを編集します。 NAFXCWD.LIB」を変更します。LIB から Mfcに移動し、NAFXCW を変更します。LIB から Mfcxx.dll にします。 LIBC を置き換えます。LIB と MSVCRT.DLL。変数. 他の MFC ライブラリと同様に、すべての C ランタイムライブラリの**前に**、mfcを使用することが重要です。

必要に応じて、製品版とデバッグ用の両方のリソースコンパイラオプションを追加**または D_AFXDLL**します (リソースを実際に **/r**を使用してコンパイルします)。 これにより、MFC Dll に存在するリソースを共有することで、最終的な実行可能ファイルが小さくなります。

これらの変更を行った後は、完全な再構築が必要です。

### <a name="building-the-samples"></a>サンプルのビルド

ほとんどの MFC サンプルプログラムは、Visual C++ から、またはコマンドラインから共有の NMAKE と互換性のあるメイクファイルからビルドできます。

これらのサンプルのいずれかを MFCxx.DLL 使用するように変換するには、を読み込むことができます。MAK ファイルを Visual C++ に挿入し、前述のようにプロジェクトオプションを設定します。 NMAKE ビルドを使用している場合は、NMAKE のコマンドラインで "AFXDLL = 1" を指定すると、共有 MFC ライブラリを使用してサンプルがビルドされます。

MFC の高度な概念のサンプル[DLLHUSK](../overview/visual-cpp-samples.md)は、MFC の DLL バージョンでビルドされます。 このサンプルでは、MFCxx.DLL にリンクされたアプリケーションを構築する方法を説明するだけでなく、このテクニカルノートで後ほど説明する MFC 拡張 Dll などの MFC DLL パッケージオプションのその他の機能についても説明します。

### <a name="packaging-notes"></a>パッケージのメモ

製品版の Dll (Mfcxx.dll [U])。DLL) は自由に再配布できます。 デバッグバージョンの Dll は自由に再配布できないため、アプリケーションの開発中にのみ使用してください。

デバッグ情報と共にデバッグ Dll が提供されます。 Visual C++ デバッガーを使用すると、DLL だけでなく、アプリケーションの実行をトレースできます。 リリース Dll (Mfcxx.dll [U])。DLL) にデバッグ情報が含まれていません。

Dll をカスタマイズまたは再構築する場合は、MFC SRC ファイル MFCDLL の "Mfcxx.dll" 以外のものを呼び出す必要があります。MAK では、ビルドオプションについて説明し、DLL の名前を変更するためのロジックが含まれています。 これらの Dll は多くの MFC アプリケーションで共有される可能性があるため、ファイルの名前を変更する必要があります。 MFC Dll のカスタムバージョンを使用すると、システムにインストールされている mfc dll を置き換えることができます。

MFC Dll を再構築することはお勧めできません。

## <a name="how-the-mfcxxdll-is-implemented"></a><a name="_mfcnotes_how_the_mfc30.dll_is_implemented"></a>MFCxx.DLL の実装方法

次のセクションでは、MFC DLL (MFCxx.DLL と MFCxxD.DLL) の実装方法について説明します。 アプリケーションで MFC DLL を使用するだけでよい場合は、ここで詳細を理解することも重要です。 ここでは、MFC 拡張 DLL の記述方法を理解するうえでの詳細については説明しませんが、この実装を理解すると、独自の DLL を記述するのに役立ちます。

### <a name="implementation-overview"></a>実装の概要

MFC DLL は、既に説明したように、MFC 拡張 DLL の特殊なケースです。 多数のクラスのエクスポートが非常に多数あります。 MFC DLL には、通常の MFC 拡張 DLL よりも特殊な機能が追加されています。

### <a name="win32-does-most-of-the-work"></a>ほとんどの作業を Win32 で実行

16ビットバージョンの MFC では、スタックセグメント上のアプリごとのデータ、いくつかの80x86 アセンブリコードによって作成された特殊なセグメント、プロセスごとの例外コンテキスト、その他の手法など、さまざまな特殊な手法が必要でした。 Win32 は、DLL 内のプロセスごとのデータを直接サポートします。これは、ほとんどの場合に必要です。 ほとんどの場合 MFCxx.DLL は NAFXCW だけです。LIB は DLL にパッケージ化されています。 MFC のソースコードを見ると、#ifdef _AFXDLL はほとんどありません。これは、特別なケースはほとんどありません。 特に、Windows 3.1 (Win32s とも呼ばれます) で Win32 を処理する特殊なケースがあります。 Win32s では、プロセスごとの DLL データを直接サポートしていないので、MFC DLL はスレッドローカルストレージ (TLS) の Win32 Api を使用してプロセスのローカルデータを取得する必要があります。

### <a name="impact-on-library-sources-additional-files"></a>ライブラリソース、追加ファイルへの影響

通常の MFC クラスライブラリのソースとヘッダーへの **_AFXDLL**バージョンの影響は比較的軽微です。 特別なバージョンのファイル (AFXV_DLL があります。H) だけでなく、追加のヘッダーファイル (AFXDLL_。H) がメイン AFXWIN.H によって含まれています。H ヘッダー。 AFXDLL_。H ヘッダーには、 `CDynLinkLibrary` `_AFXDLL` アプリケーションと MFC 拡張 dll のクラスおよびその他の実装の詳細が含まれています。 AFXDLLX。H ヘッダーは、MFC 拡張 Dll をビルドするために用意されています (詳細については、上記を参照してください)。

MFC SRC の MFC ライブラリに対する通常のソースには、#ifdef の下に追加の条件付きコードがいくつかあり `_AFXDLL` ます。 追加のソースファイル (DLLINIT)。CPP) には、MFC の共有バージョン用の追加の DLL 初期化コードおよびその他のグルーが含まれています。

MFC の共有バージョンをビルドするために、追加のファイルが用意されています。 (DLL をビルドする方法の詳細については、以下を参照してください)。

- 回.DEF ファイルは、DLL の debug (MFCxxD .DEF) バージョンおよび release (Mfcxx.dll) バージョンの MFC DLL エントリポイントをエクスポートするために使用されます。

- 込み.RC ファイル (MFCDLL。RC) には、すべての標準 MFC リソースと DLL の VERSIONINFO リソースが含まれています。

- ある.CLW ファイル (MFCDLL。CLW) は、ClassWizard を使用して MFC クラスを参照できるようにするために用意されています。 メモ: この機能は、MFC の DLL バージョンに固有のものではありません。

### <a name="memory-management"></a>メモリ管理

MFCxx.DLL を使用するアプリケーションは、共有の C ランタイム DLL MSVCRTxx.DLL によって提供される共通のメモリアロケーターを使用します。 アプリケーション、MFC 拡張 Dll、および MFC Dll 自体は、この共有メモリアロケーターを使用します。 メモリ割り当てに共有 DLL を使用することにより、MFC Dll は、後でアプリケーションによって解放されるメモリまたはその逆のメモリを割り当てることができます。 アプリケーションと DLL は両方とも同じアロケーターを使用する必要があるため、C++ のグローバル**演算子 new**または**operator delete**をオーバーライドしないでください。 その他の C ランタイムメモリ割り当てルーチン ( **malloc**、 **realloc**、 **free**など) にも同じルールが適用されます。

### <a name="ordinals-and-class-__declspecdllexport-and-dll-naming"></a>序数およびクラス __declspec (dllexport) と DLL の名前付け

`class` **`__declspec(dllexport)`** C++ コンパイラの機能は使用しません。 代わりに、クラスライブラリソース (Mfcxx.dll および Mfc) にエクスポートの一覧が含まれています。 これらのエントリポイントセット (関数とデータ) のみがエクスポートされます。 MFC のプライベート実装関数やクラスなどの他のシンボルはエクスポートされません。すべてのエクスポートは、組み込みまたは非常駐の名前テーブルに文字列名のない序数によって行われます。

を使用する `class` **`__declspec(dllexport)`** と、より小さな dll を構築するための代替手段となりますが、MFC のような大きな dll の場合は、既定のエクスポートメカニズムに効率と容量の制限があります。

これは、実行や読み込みの速度を大幅に低下させずに 800 KB 程度しかない、リリース MFCxx.DLL に大量の機能をパッケージ化できることを意味します。 この手法が使用されていない場合、MFCxx.DLL は10万になります。 これにより、の末尾にエントリポイントを追加することもできます。序数によるエクスポートの速度とサイズの効率を損なうことなく単純なバージョン管理を可能にする DEF ファイル。 MFC クラスライブラリのメジャーバージョンのリビジョンによって、ライブラリ名が変更されます。 つまり、MFC30.DLL は、MFC クラスライブラリのバージョン3.0 を含む再頒布可能な DLL です。 この DLL のアップグレード (たとえば、架空の MFC 3.1 では、DLL に MFC31.DLL という名前が付けられます。 ここでも、mfc のソースコードを変更して MFC DLL のカスタムバージョンを生成する場合は、別の名前を使用します (名前に "MFC" を付けないことをお勧めします)。

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
