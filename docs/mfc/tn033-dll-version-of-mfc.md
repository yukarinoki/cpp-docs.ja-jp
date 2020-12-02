---
title: 'テクニカル ノート 33: MFC の DLL バージョン'
description: Mfc アプリケーションと mfc 拡張 Dll で MFC 共有ダイナミックリンクライブラリを使用する方法について説明します。
ms.date: 11/30/2020
helpviewer_keywords:
- MFC DLLs [MFC], writing MFC extension DLLS
- AFXDLL library
- DLLs [MFC], MFC
- DLL version of MFC [MFC]
- TN033
ms.openlocfilehash: b9330fe7c756f962a8b06a04b840bfda343f3a49
ms.sourcegitcommit: 432c24dde31c400437c4320e8432b1ddb232f844
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2020
ms.locfileid: "96440312"
---
# <a name="tn033-dll-version-of-mfc"></a>テクニカル ノート 33: MFC の DLL バージョン

このメモでは、 *`MFCxx.DLL`* *`MFCxxD.DLL`* mfc アプリケーションと Mfc 拡張 dll を使用して、( *xx* は mfc バージョン番号) 共有ダイナミックリンクライブラリを使用する方法について説明します。 通常の MFC Dll の詳細については、「 [DLL の一部としての mfc の使用](../mfc/tn011-using-mfc-as-part-of-a-dll.md)」を参照してください。

このテクニカルノートでは、Dll の3つの側面について説明します。 最後の2つは、より高度なユーザー向けです。

- [MFC 拡張 DLL のビルド方法](#_mfcnotes_how_to_write_an_mfc_extension_dll)

- [MFC の DLL バージョンを使用する MFC アプリケーションのビルド方法](#_mfcnotes_writing_an_application_that_uses_the_dll_version)

- [MFC 共有ダイナミックリンクライブラリの実装方法](#_mfcnotes_how_the_mfc30.dll_is_implemented)

Mfc を使用した DLL の構築に関心がある場合は ( *通常の MFC DLL* と呼ばれます)、mfc 以外のアプリケーションで使用できます。 [テクニカルノート 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md)を参照してください。

## <a name="overview-of-mfcxxdll-support-terminology-and-files"></a>MFCxx.DLL サポートの概要: 用語とファイル

**レギュラー MFC dll**: mfc の一部のクラスを使用して、スタンドアロン dll を構築するには、通常の mfc dll を使用します。 アプリケーション/DLL の境界を越えたインターフェイスは "C" インターフェイスであり、クライアントアプリケーションは MFC アプリケーションである必要はありません。

MFC 1.0 でサポートされている Dll のバージョンは、通常の MFC Dll です。 詳細については、「 [テクニカルノート 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md) 」と「MFC の高度な概念」のサンプルを参照して [`DLLScreenCap`](../overview/visual-cpp-samples.md) ください。

> [!NOTE]
> Visual C++ バージョン4.0 では、 **USRDLL** という用語は互換性のために残されており、mfc と静的にリンクする通常の mfc DLL に置き換えられています。 MFC と動的にリンクするレギュラー MFC DLL をビルドすることもできます。

MFC 3.0 (およびそれ以降) では、OLE クラスとデータベースクラスを含む、すべての新機能を備えた通常の MFC Dll がサポートされています。

**AFXDLL**: MFC ライブラリの共有バージョンとも呼ばれます。 これは、MFC 2.0 で追加された新しい DLL サポートです。 MFC ライブラリ自体は、次に説明する多くの Dll に含まれています。 クライアントアプリケーションまたは DLL は、必要な Dll を動的にリンクします。 アプリケーション/DLL の境界を越えたインターフェイスは、C++/MFC クラスのインターフェイスです。 クライアントアプリケーションは、MFC アプリケーションである必要があります。 この DLL は、MFC 3.0 のすべての機能をサポートしています (ただし、データベースクラスでは UNICODE はサポートされていません)。

> [!NOTE]
> Visual C++ バージョン4.0 では、このタイプの DLL は "拡張 DLL" と呼ばれます。

このメモでは、を使用して *`MFCxx.DLL`* MFC DLL セット全体を参照します。これには次のものが含まれます。

- Debug: *`MFCxxD.DLL`* (結合) と *`MFCSxxD.LIB`* (static)。

- リリース: *`MFCxx.DLL`* (結合) と *`MFCSxx.LIB`* (静的)。

- Unicode デバッグ: *`MFCxxUD.DLL`* (組み合わせ) と *`MFCSxxD.LIB`* (static)。

- Unicode リリース: *`MFCxxU.DLL`* (結合) と *`MFCSxxU.LIB`* (static)。

> [!NOTE]
> これらのライブラリは、 *`MFCSxx[U][D].LIB`* MFC の共有 dll と共に使用されます。 これらのライブラリには、アプリケーションまたは DLL に静的にリンクする必要があるコードが含まれています。

アプリケーションは、対応するインポートライブラリにリンクします。

- デバック *`MFCxxD.LIB`*

- 解除 *`MFCxx.LIB`*

- Unicode デバッグ: *`MFCxxUD.LIB`*

- Unicode リリース: *`MFCxxU.LIB`*

*Mfc 拡張 dll* は、 *`MFCxx.DLL`* (またはその他の MFC 共有 dll) を拡張する dll です。 ここでは、MFC コンポーネントアーキテクチャを開始します。 MFC クラスから有用なクラスを派生させたり、別の MFC に似たツールキットをビルドしたりする場合は、DLL に配置できます。 *`MFCxx.DLL`* 最終的なクライアントアプリケーションと同様に、DLL でが使用されます。 MFC 拡張 DLL は、再利用可能なリーフクラス、再利用可能な基底クラス、および再利用可能なビューおよびドキュメントクラスを許可します。

## <a name="pros-and-cons"></a>長所と短所

MFC の共有バージョンを使用する理由

- 共有ライブラリを使用すると、アプリケーションのサイズが小さくなることがあります。 (ほとんどの MFC ライブラリを使用する最小アプリケーションは、10K 未満です)。

- MFC の共有バージョンでは、MFC 拡張 Dll と通常の MFC Dll がサポートされています。

- 静的にリンクされた MFC アプリケーションとは異なり、共有 MFC ライブラリを使用するアプリケーションを作成する方が高速です。 これは、MFC 自体をリンクする必要がないためです。 **`DEBUG`** リンカーがデバッグ情報を圧縮する必要があるビルドでは特に当てはまります。 デバッグ情報が既に含まれている DLL にアプリケーションをリンクした場合、圧縮するデバッグ情報は少なくなります。

MFC の共有バージョンを使用しないのはなぜですか。

- 共有ライブラリを使用するアプリケーションを配布するには、 *`MFCxx.DLL`* とその他のライブラリをプログラムに発送する必要があります。 *`MFCxx.DLL`* は多くの Dll のように自由に再配布できますが、セットアッププログラムに DLL をインストールする必要があります。 また、プログラムと MFC Dll の両方で使用されるその他の再頒布可能ライブラリを発送する必要があります。

## <a name="how-to-write-an-mfc-extension-dll"></a><a name="_mfcnotes_how_to_write_an_mfc_extension_dll"></a> 方法: MFC 拡張 DLL を記述する

MFC 拡張 DLL は、MFC クラスの機能を拡張するためのクラスと関数を含む DLL です。 MFC 拡張 DLL は、アプリケーションで使用されるのと同じ方法で共有 MFC Dll を使用します。追加の考慮事項がいくつかあります。

- ビルドプロセスは、共有 MFC ライブラリを使用するアプリケーションをビルドする場合と似ていますが、いくつかの追加のコンパイラオプションとリンカーオプションがあります。

- MFC 拡張 DLL には、の派生クラスがありません `CWinApp` 。

- MFC 拡張 DLL では、特別なを提供する必要があり `DllMain` ます。 AppWizard には、変更可能な関数が用意さ `DllMain` れています。

- Mfc 拡張 dll が `CDynLinkLibrary` `CRuntimeClass` 型またはリソースをアプリケーションにエクスポートする場合、MFC 拡張 dll は通常、を作成するための初期化ルーチンを提供します。 `CDynLinkLibrary`アプリケーションごとのデータを MFC 拡張 DLL で維持する必要がある場合は、の派生クラスを使用できます。

これらの考慮事項については、以下で詳しく説明します。 MFC の高度な概念のサンプルも参照してください [`DLLHUSK`](../overview/visual-cpp-samples.md) 。 次の方法を示します。

- 共有ライブラリを使用してアプリケーションをビルドします。 ( *`DLLHUSK.EXE`* は、mfc ライブラリおよびその他の dll と動的にリンクする mfc アプリケーションです)。

- MFC 拡張 DLL をビルドします。 ( `_AFXEXT` MFC 拡張 DLL をビルドするときに、get などの特別なフラグがどのように使用されるかを示しています)。

- MFC 拡張 Dll の2つの例をビルドします。 1つは、制限付きエクスポート (TESTDLL1) を使用した MFC 拡張 DLL の基本構造を示し、もう1つはクラスインターフェイス全体 (TESTDLL2) をエクスポートする方法を示しています。

クライアントアプリケーションと MFC 拡張 Dll の両方で、同じバージョンのを使用する必要があり *`MFCxx.DLL`* ます。 MFC Dll の規則に従い、MFC 拡張 DLL のデバッグバージョンとリリース () バージョンの両方を提供し **`/release`** ます。 これにより、クライアントプログラムは、アプリケーションのデバッグバージョンとリリースバージョンの両方をビルドし、すべての Dll の適切なデバッグバージョンまたはリリースバージョンにリンクすることができます。

> [!NOTE]
> C++ の名前の変形とエクスポートの問題のため、MFC 拡張 DLL からのエクスポートの一覧は、同じ DLL のデバッグバージョンとリリースバージョンとプラットフォームによって異なる場合があります。 リリースで *`MFCxx.DLL`* は、約2000のエントリポイントがエクスポートされています。デバッグに *`MFCxxD.DLL`* は約3000のエントリポイントがエクスポートされています。

### <a name="quick-note-on-memory-management"></a>メモリ管理に関するクイックメモ

このテクニカルノートの最後にある「メモリ管理」というタイトルのセクションでは、 *`MFCxx.DLL`* MFC の共有バージョンを使用したの実装について説明しています。 MFC 拡張 DLL だけを実装するために必要な情報については、ここで説明します。

*`MFCxx.DLL`* また、クライアントアプリケーションのアドレス空間に読み込まれたすべての MFC 拡張 Dll は、同じアプリケーション内にあるかのように、同じメモリアロケーター、リソース読み込み、およびその他の MFC の "グローバル" 状態を使用します。 Mfc に静的にリンクする非 MFC DLL ライブラリと通常の MFC Dll では、厳密には逆の処理が行われるため、これは重要です。各 DLL は独自のメモリプールから割り当てられます。

MFC 拡張 DLL がメモリを割り当てると、そのメモリは他のアプリケーションで割り当てられたオブジェクトと自由に混在させることができます。 また、共有 MFC ライブラリを使用するアプリケーションがクラッシュした場合、オペレーティングシステムは DLL を共有する他のすべての MFC アプリケーションの整合性を維持します。

同様に、リソースの読み込み元となる現在の実行可能ファイルなど、他の "グローバルな" MFC の状態も、クライアントアプリケーション、すべての MFC 拡張 Dll、およびそれ自体の間で共有さ *`MFCxx.DLL`* れます。

### <a name="building-an-mfc-extension-dll"></a>MFC 拡張 DLL のビルド

AppWizard を使用して MFC 拡張 DLL プロジェクトを作成すると、適切なコンパイラとリンカーの設定が自動的に生成されます。 また、 `DllMain` 変更できる関数も生成されます。

既存のプロジェクトを MFC 拡張 DLL に変換する場合は、MFC の共有バージョンを使用してビルドする標準設定から開始します。 その後、次の変更を行います。

- **`/D_AFXEXT`** をコンパイラフラグに追加します。 [プロジェクトのプロパティ] ダイアログボックスで、[ **C/c + +**] [  >  **プリプロセッサ**] カテゴリを選択します。 [ `_AFXEXT` マクロの **定義** ] フィールドにを追加して、各項目をセミコロンで区切ります。

- **`/Gy`** コンパイラスイッチを削除します。 [プロジェクトのプロパティ] ダイアログボックスで、[ **C/c + +**  >  **コード生成**] カテゴリを選択します。 [ **Function-Level リンクを有効にする** ] プロパティが有効になっていないことを確認します。 この設定により、参照されていない関数がリンカーによって削除されないため、クラスのエクスポートが容易になります。 元のプロジェクトで、MFC に静的にリンクされているレギュラー MFC DLL をビルドした場合は、 **`/MT`** (または **`/MTd`** ) コンパイラオプションを **`/MD`** (または) に変更し **`/MDd`** ます。

- リンクするオプションを使用して、エクスポートライブラリを作成 **`/DLL`** します。 このオプションは、新しいターゲットを作成し、ターゲットの種類として Win32 Dynamic-Link ライブラリを指定するときに設定されます。

### <a name="changing-your-header-files"></a>ヘッダーファイルの変更

MFC 拡張 DLL の通常の目的は、その機能を使用できる1つ以上のアプリケーションにいくつかの共通機能をエクスポートすることです。 基本的に、DLL は、クライアントアプリケーションで使用するクラスとグローバル関数をエクスポートします。

各メンバー関数がインポートまたはエクスポート用に適切にマークされていることを確認するには、特別な宣言 `__declspec(dllexport)` とを使用し `__declspec(dllimport)` ます。 クライアントアプリケーションでクラスを使用する場合は、として宣言する必要が `__declspec(dllimport)` あります。 MFC 拡張 DLL 自体をビルドする場合は、関数をとして宣言する必要があり `__declspec(dllexport)` ます。 また、ビルドされた DLL は、読み込み時にクライアントプログラムがそれらにバインドできるように、関数をエクスポートする必要があります。

クラス全体をエクスポートするには、 `AFX_EXT_CLASS` クラス定義でを使用します。 `__declspec(dllexport)`とが定義されている場合と同様に、フレームワークはこのマクロを定義しますが、が定義されていない場合として `_AFXDLL` `_AFXEXT` 定義し `__declspec(dllimport)` `_AFXEXT` ます。 `_AFXEXT` は、MFC 拡張 DLL をビルドするときにのみ定義されます。 次に例を示します。

```cpp
class AFX_EXT_CLASS CExampleExport : public CObject
{ /* ... class definition ... */ };
```

### <a name="not-exporting-the-entire-class"></a>クラス全体をエクスポートしない

場合によっては、クラスに必要な個々のメンバーだけをエクスポートする必要があります。 たとえば、から派生したクラスをエクスポートする場合は、 `CDialog` コンストラクターと呼び出しをエクスポートするだけで済み `DoModal` ます。 これらのメンバーは DLL の DEF ファイルを使用してエクスポートできますが、 `AFX_EXT_CLASS` エクスポートに必要な個々のメンバーでもほぼ同じ方法でを使用できます。

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

この場合、クラスのすべてのメンバーをエクスポートしないため、追加の問題が発生する可能性があります。 この問題は、MFC マクロの動作方法にあります。 MFC のヘルパー マクロのいくつかは、実際にデータ メンバーを宣言または定義します。 DLL でも、これらのデータメンバーをエクスポートする必要があります。

たとえば、MFC 拡張 DLL をビルドするときに、DECLARE_DYNAMIC マクロは次のように定義されます。

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
    static CRuntimeClass* PASCAL _GetBaseClass(); \
    public: \
    static AFX_DATA CRuntimeClass class##class_name; \
    virtual CRuntimeClass* GetRuntimeClass() const; \
```

`static AFX_DATA`クラス内の静的オブジェクトの宣言を開始する行。 このクラスを正しくエクスポートし、クライアントの実行時情報にアクセスするには、この静的オブジェクトをエクスポートする必要があります。 静的オブジェクトは修飾子を使用して宣言されているため `AFX_DATA` 、 `AFX_DATA` `__declspec(dllexport)` DLL のビルド時にを定義するだけで済みます。 これは、 `__declspec(dllimport)` クライアントの実行可能ファイルをビルドするときにとして定義します。

前に説明したように、 `AFX_EXT_CLASS` は既にこの方法で定義されています。 再定義する必要があるのは、 `AFX_DATA` クラス定義の場合と同じにすることだけ `AFX_EXT_CLASS` です。

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

同じ手法を使用して、 `CArchive` DECLARE_SERIAL および IMPLEMENT_SERIAL マクロを使用するクラスの抽出演算子を自動的にエクスポートできます。 次のコードを使用して、(ヘッダーファイルにある) クラス宣言を角かっこで示して、archive 演算子をエクスポートします。

```cpp
#undef AFX_API
#define AFX_API AFX_EXT_CLASS

/* your class declarations here */

#undef AFX_API
#define AFX_API
```

### <a name="limitations-of-_afxext"></a>_AFXEXT の制限事項

Mfc 拡張 dll `_AFXEXT` の複数のレイヤーがない限り、mfc 拡張 dll のプリプロセッサシンボルを使用できます。 MFC クラスから派生する独自の MFC 拡張 DLL のクラスがあり、そこから呼び出すか派生する MFC 拡張 DLL がある場合は、あいまいさを避けるために独自のプリプロセッサ シンボルを使用する必要があります。

この問題は、Win32 では、DLL からエクスポートするデータを明示的に宣言 `__declspec(dllexport)` し、dll からインポートする必要があることです `__declspec(dllimport)` 。 を定義する場合 `_AFXEXT` 、MFC ヘッダーは `AFX_EXT_CLASS` が正しく定義されていることを確認します。

複数のレイヤーがある場合、などの1つのシンボルでは十分では `AFX_EXT_CLASS` ありません。 mfc 拡張 Dll は独自のクラスをエクスポートし、別の mfc 拡張 dll から他のクラスをインポートすることもできます。 この問題に対処するには、DLL を使用するのではなく、DLL 自体をビルドしていることを示す特別なプリプロセッサシンボルを使用します。 たとえば、、、およびという2つの MFC 拡張 Dll を考えてみ *`A.DLL`* *`B.DLL`* ます。 各クラスは、それぞれとのクラスをそれぞれエクスポートし *`A.H`* *`B.H`* ます。 *`B.DLL`* は、のクラスを使用し *`A.DLL`* ます。 ヘッダー ファイルは次のようになります。

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

を構築すると、を使用してビルドされ、 *`A.DLL`* **`/DA_IMPL`** が構築されるときに、を使用してビルドされ *`B.DLL`* **`/DB_IMPL`** ます。 DLL ごとに個別のシンボルを使用することにより、 `CExampleB` がエクスポートされ、 `CExampleA` ビルド時にインポートされ *`B.DLL`* ます。 `CExampleA`*`A.DLL`* *`B.DLL`* は、または他のクライアントによって使用されるときに、ビルドおよびインポート時にエクスポートされます。

組み込み `AFX_EXT_CLASS` `_AFXEXT` シンボルおよびプリプロセッサシンボルを使用する場合、この種のレイヤーは実行できません。 前述の手法では、MFC と同じようにこの問題を解決します。 MFC では、OLE、データベース、およびネットワーク MFC 拡張 Dll をビルドするときに、この手法を使用します。

### <a name="not-exporting-the-entire-class"></a>クラス全体をエクスポートしない

ここでも、クラス全体をエクスポートしない場合は、特別な注意が必要です。 MFC マクロによって作成された必要なデータ項目が正しくエクスポートされていることを確認します。 これは、 `AFX_DATA` 特定のクラスのマクロに再定義することによって行うことができます。 クラス全体をエクスポートしない場合は、常に再定義します。

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

ここでは、MFC 拡張 DLL のメインソースファイルに配置する必要があるコードを示します。 これは、標準のに含まれています。 AppWizard を使用して MFC 拡張 DLL のスターターファイルを作成すると、が提供さ `DllMain` れます。

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

を呼び出すと、 `AfxInitExtensionModule` オブジェクトの作成時に後で使用するために、モジュールのランタイムクラス ( `CRuntimeClass` 構造体) とそのオブジェクトファクトリ ( `COleObjectFactory` オブジェクト) がキャプチャされ `CDynLinkLibrary` ます。 (省略可能) の呼び出しに `AfxTermExtensionModule` より、各プロセスがデタッチされたとき (プロセスが終了したとき、または dll が呼び出しによってアンロードされたとき) に mfc 拡張 dll をクリーンアップでき `FreeLibrary` ます。 ほとんどの MFC 拡張 Dll は動的に読み込まれないため (通常はインポートライブラリを使用してリンクされているため)、の呼び出しは `AfxTermExtensionModule` 通常必要ありません。

アプリケーションで MFC 拡張 Dll を動的に読み込んで解放する場合は、上記のように、を必ず呼び出し `AfxTermExtensionModule` てください。 また `AfxLoadLibrary` 、 `AfxFreeLibrary` `LoadLibrary` `FreeLibrary` アプリケーションで複数のスレッドを使用する場合、または MFC 拡張 DLL を動的に読み込む場合は、(Win32 関数およびではなく) とを使用してください。 およびを使用する `AfxLoadLibrary` と、 `AfxFreeLibrary` MFC 拡張 DLL が読み込まれてアンロードされるときに実行される起動コードとシャットダウンコードが、mfc のグローバル状態を破壊することはありません。

ヘッダーファイルには、 *`AFXDLLX.H`* およびの定義など、MFC 拡張 dll で使用される構造体の特別な定義が含まれてい `AFX_EXTENSION_MODULE` `CDynLinkLibrary` ます。

グローバル *Extensiondll* は、示されているように宣言する必要があります。 16ビットバージョンの MFC とは異なり、この時点では、 *`MFCxx.DLL`* が呼び出された時点でが完全に初期化されるため、メモリを割り当てて mfc 関数を呼び出すことができ `DllMain` ます。

### <a name="sharing-resources-and-classes"></a>リソースやクラスの共有

単純な MFC 拡張 Dll では、クライアントアプリケーションに少数の低帯域幅の関数をエクスポートするだけで済みます。 ユーザーインターフェイスを多用する Dll の多くは、リソースと C++ クラスをクライアントアプリケーションにエクスポートすることが必要になる場合があります。

リソースのエクスポートには、リソース リストを使います。 各アプリケーションは、オブジェクトの単一のリンクリストです `CDynLinkLibrary` 。 リソースを検索する場合、リソースを読み込む標準的な MFC 実装のほとんどは、まず現在のリソースモジュール ( `AfxGetResourceHandle` ) を参照し、見つからない場合は、要求されたリソースを読み込もうとしているオブジェクトの一覧を確認し `CDynLinkLibrary` ます。

C++ クラス名が指定された C++ オブジェクトの動的作成も同様です。 MFC オブジェクトの逆シリアル化機構には、前に格納され `CRuntimeClass` た内容に基づいて、必要な型の C++ オブジェクトを動的に作成することによって再構築できるように、すべてのオブジェクトが登録されている必要があります。

クライアントアプリケーションで MFC 拡張 DLL のクラスを使用する場合は `DECLARE_SERIAL` 、クラスをエクスポートしてクライアントアプリケーションに表示されるようにする必要があります。 また、リストを調べても実行でき `CDynLinkLibrary` ます。

MFC の高度な概念のサンプルでは、 [`DLLHUSK`](../overview/visual-cpp-samples.md) リストは次のようになります。

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

*`MFCxx.DLL`* 通常、エントリはリソースとクラスの一覧の最後にあります。 *`MFCxx.DLL`* すべての標準コマンド Id のプロンプト文字列を含む、すべての標準 MFC リソースが含まれています。 リストの末尾に配置すると、Dll とクライアントアプリケーション自体が、独自のコピーを作成するのではなく、内の共有リソースに依存するようになり *`MFCxx.DLL`* ます。

すべての Dll のリソースとクラス名をクライアントアプリケーションの名前空間にマージすると、選択した Id または名前に注意する必要があるという欠点があります。 この機能を無効にするには、リソースまたはオブジェクトをクライアントアプリケーションにエクスポートしないようにし `CDynLinkLibrary` ます。 このサンプルでは、 [`DLLHUSK`](../overview/visual-cpp-samples.md) 複数のヘッダーファイルを使用して、共有リソースの名前空間を管理します。 共有リソースファイルの使用に関するその他のヒントについては、「 [テクニカルノート 35](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md) 」を参照してください。

### <a name="initializing-the-dll"></a>DLL の初期化

既に説明したように、通常は、 `CDynLinkLibrary` リソースとクラスをクライアントアプリケーションにエクスポートするオブジェクトを作成します。 DLL を初期化するには、エクスポートされたエントリポイントを指定する必要があります。 少なくとも、 `void` 引数を取らず、何も返さないルーチンですが、任意のものを指定できます。

この方法を使用する場合は、DLL を使用する各クライアントアプリケーションが、この初期化ルーチンを呼び出す必要があります。 を呼び出した直後に、このオブジェクトをに割り当てることもでき `CDynLinkLibrary` `DllMain` `AfxInitExtensionModule` ます。

初期化ルーチンは、現在の `CDynLinkLibrary` アプリケーションのヒープにオブジェクトを作成する必要があります。このとき、MFC 拡張 DLL 情報に接続します。 これを行うには、次のような関数を定義します。

```cpp
extern "C" extern void WINAPI InitXxxDLL()
{
    new CDynLinkLibrary(extensionDLL);
}
```

この例の一般的な名前である *Initxxx dll* は、任意のものにすることができます。 これは必要ありません **`extern "C"`** が、エクスポートリストの保守が容易になります。

> [!NOTE]
> 通常の MFC DLL から MFC 拡張 DLL を使用する場合は、この初期化関数をエクスポートする必要があります。 MFC 拡張 DLL クラスまたはリソースを使用する前に、通常の MFC DLL からこの関数を呼び出す必要があります。

### <a name="exporting-entries"></a>エクスポート (エントリを)

クラスをエクスポートする簡単な方法は、 `__declspec(dllimport)` `__declspec(dllexport)` エクスポートする各クラスおよびグローバル関数でおよびを使用することです。 これははるかに簡単ですが、以下で説明するように DEF ファイル内の各エントリポイントに名前を付けるよりも効率が悪くなります。 これは、エクスポートされる関数の制御が少ないためです。 また、関数を序数でエクスポートすることはできません。 TESTDLL1 と TESTDLL2 は、このメソッドを使用してエントリをエクスポートします。

より効率的な方法は、DEF ファイルに名前を付けて各エントリをエクスポートすることです。 このメソッドは、によって使用され *`MFCxx.DLL`* ます。 DLL から選択的にエクスポートするため、エクスポートする特定のインターフェイスを決定する必要があります。 DEF ファイルのエントリの形式で、破損した名前をリンカーに指定する必要があるため、これは困難です。 C++ クラスのシンボリックリンクが本当に必要でない限り、エクスポートしないでください。

以前に DEF ファイルを使用して C++ クラスをエクスポートしようとした場合は、このリストを自動的に生成するツールを開発することをお勧めします。 これを行うには、2段階のリンクプロセスを使用します。 DLL をエクスポートせずに1回リンクし、リンカーがマップファイルを生成できるようにします。 マップファイルには、エクスポートする必要がある関数の一覧が含まれています。 再配置によっては、これを使用して DEF ファイルのエクスポートエントリを生成できます。 *`MFCxx.DLL`* と OLE およびデータベース MFC 拡張 dll のエクスポートリストは、このようなプロセスを使用して生成されました (ただし、完全には自動ではありませんが、しばらくの間に1回は手動でチューニングする必要があります)。

### <a name="cwinapp-vs-cdynlinklibrary"></a>CWinApp と CDynLinkLibrary

MFC 拡張 DLL には、 `CWinApp` 独自のの派生オブジェクトがありません。 代わりに、 `CWinApp` クライアントアプリケーションのから派生したオブジェクトを使用する必要があります。 これは、クライアントアプリケーションがメインメッセージポンプ、アイドルループなどを所有していることを意味します。

MFC 拡張 DLL で、アプリケーションごとに追加のデータを保持する必要がある場合は、から新しいクラスを派生させ、上記のルーチンで作成することができ `CDynLinkLibrary` `InitXxxDLL` ます。 DLL を実行すると、現在のアプリケーションのオブジェクトの一覧をチェックして、 `CDynLinkLibrary` その特定の MFC 拡張 DLL のオブジェクトを見つけることができます。

### <a name="using-resources-in-your-dll-implementation"></a>DLL 実装でのリソースの使用

前述のように、既定のリソースの読み込みでは、 `CDynLinkLibrary` 要求されたリソースを持つ最初の EXE または DLL を検索するオブジェクトの一覧が表示されます。 すべての MFC Api とすべての内部コードで、リソースリストを使用してリソースの `AfxFindResourceHandle` 一覧を調べ、リソースがどこにあるかに関係なく検索します。

特定の場所からのみリソースを読み込む場合は、Api およびを使用して、 `AfxGetResourceHandle` `AfxSetResourceHandle` 古いハンドルを保存し、新しいハンドルを設定します。 クライアント アプリケーションに戻る前に、元のリソース ハンドルを必ず復元してください。 このサンプル TESTDLL2 では、この方法を使用してメニューを明示的に読み込みます。

リストをウォークすることにはいくつかの欠点があります。少し遅く、リソース ID 範囲の管理が必要です。 いくつかの MFC 拡張 DLL にリンクされるクライアント アプリケーション側で、DLL のインスタンス ハンドルを指定しなくても、DLL が提供する任意のリソースを使用できるという利点もあります。 `AfxFindResourceHandle` は、リソース リストを検索して一致するリソースを見つけるのに使われる API です。 リソースの名前と型を受け取り、リソースを最初に検出したリソースハンドル、または NULL を返します。

## <a name="writing-an-application-that-uses-the-dll-version"></a><a name="_mfcnotes_writing_an_application_that_uses_the_dll_version"></a> DLL バージョンを使用するアプリケーションの作成

### <a name="application-requirements"></a>アプリケーションの要件

MFC の共有バージョンを使用するアプリケーションは、いくつかの基本的な規則に従う必要があります。

- これには、オブジェクトがあり、 `CWinApp` メッセージポンプの標準規則に従う必要があります。

- このメソッドは、必要なコンパイラフラグのセット (下記参照) を使用してコンパイルする必要があります。

- これは、Mfcxx.dll インポートライブラリとリンクする必要があります。 必要なコンパイラフラグを設定することにより、MFC ヘッダーは、アプリケーションをリンクする必要があるライブラリをリンク時に決定します。

- 実行可能ファイルを実行するには、を *`MFCxx.DLL`* パスまたは Windows システムディレクトリに配置する必要があります。

### <a name="building-with-the-development-environment"></a>開発環境でのビルド

ほとんどの標準既定値で内部メイクファイルを使用している場合は、プロジェクトを簡単に変更して DLL バージョンをビルドできます。

次の手順では、(デバッグ用に) および (リリース用に) にリンクされている MFC アプリケーションが正しく機能していて、 *`NAFXCWD.LIB`* *`NAFXCW.LIB`* mfc ライブラリの共有バージョンを使用するように変換することを前提としています。 Visual Studio 環境を実行していて、内部プロジェクトファイルを持っている。

1. [ **プロジェクト** ] メニューの [ **プロパティ**] をクリックします。 [ **全般** ] ページの [ **プロジェクトの既定値**] で、共有 DLL (mfcxx.dll (d) .dll) **で MFC を使用** するように Microsoft Foundation Classes を設定します。

### <a name="building-with-nmake"></a>ビルド (NMAKE を使用して)

コンパイラの外部メイクファイル機能を使用している場合、または NMAKE を直接使用している場合は、必要なコンパイラオプションとリンカーオプションをサポートするようにメイクファイルを編集する必要があります。

必要なコンパイラフラグ:

- **`/D_AFXDLL /MD`**
  **`/D_AFXDLL`**

標準の MFC ヘッダーでは、シンボルを定義する必要があり `_AFXDLL` ます。

- **`/MD`** アプリケーションでは、C ランタイムライブラリの DLL バージョンを使用する必要があります。

他のすべてのコンパイラフラグは、MFC の既定値に従います (たとえば、 `_DEBUG` デバッグの場合)。

ライブラリのリンカーリストを編集します。 *`NAFXCWD.LIB`* をに変更 *`MFCxxD.LIB`* し、 *`NAFXCW.LIB`* をに変更し *`MFCxx.LIB`* ます。 *`LIBC.LIB`* をに置き換え *`MSVCRT.LIB`* ます。 他の MFC ライブラリと同様に、 *`MFCxxD.LIB`* C ランタイムライブラリの **前に** 配置することが重要です。

必要に応じて、 **`/D_AFXDLL`** リリースとデバッグの両方のリソースコンパイラオプションをに追加します (リソースをで実際にコンパイルしたもの **`/R`** )。 このオプションを使用すると、MFC Dll に存在するリソースを共有することで、最終的な実行可能ファイルが小さくなります。

これらの変更を行った後は、完全な再構築が必要です。

### <a name="building-the-samples"></a>サンプルのビルド

ほとんどの MFC サンプルプログラムは、Visual C++ から、またはコマンドラインから共有の NMAKE と互換性のあるメイクファイルからビルドできます。

これらのサンプルのいずれかを使用するように変換するには、 *`MFCxx.DLL`* MAK ファイルを Visual C++ に読み込んで、前述のようにプロジェクトオプションを設定します。 NMAKE ビルドを使用している場合は、 `AFXDLL=1` nmake のコマンドラインでを指定すると、共有 MFC ライブラリを使用してサンプルをビルドできます。

MFC の高度な概念のサンプル [DLLHUSK](../overview/visual-cpp-samples.md) は、MFC の DLL バージョンでビルドされます。 このサンプルでは、にリンクされたアプリケーションを構築する方法を説明するだけでなく *`MFCxx.DLL`* 、このテクニカルノートで後述する mfc 拡張 dll などの MFC DLL パッケージオプションのその他の機能についても説明します。

### <a name="packaging-notes"></a>パッケージのメモ

Dll のリリースバージョン ( *`MFCxx.DLL`* および *`MFCxxU.DLL`* ) は自由に再配布できます。 Dll のデバッグバージョンは自由に再配布できないため、アプリケーションの開発中にのみ使用してください。

デバッグ情報と共にデバッグ Dll が提供されます。 Visual C++ デバッガーを使用すると、アプリケーションと DLL の両方の実行をトレースできます。 リリース Dll (および) には、 *`MFCxx.DLL`* *`MFCxxU.DLL`* デバッグ情報は含まれていません。

Dll をカスタマイズまたは再構築する場合は、"Mfcxx.dll" 以外のものを呼び出す必要があります。 MFC SRC ファイルには、 *`MFCDLL.MAK`* ビルドオプションが記述されており、DLL の名前を変更するためのロジックが含まれています。 これらの Dll は多くの MFC アプリケーションで共有される可能性があるため、ファイルの名前を変更する必要があります。 MFC Dll のカスタムバージョンを変更すると、システムにインストールされている dll が、共有 MFC Dll を使用して別の MFC アプリケーションを中断する可能性があります。

MFC Dll を再構築することは推奨されていません。

## <a name="how-the-mfcxxdll-is-implemented"></a><a name="_mfcnotes_how_the_mfc30.dll_is_implemented"></a> MFCxx.DLL の実装方法

次のセクションでは、MFC DLL (および) の実装方法について説明し *`MFCxx.DLL`* *`MFCxxD.DLL`* ます。 アプリケーションで MFC DLL を使用するだけでよい場合は、ここで詳細を理解することも重要です。 ここでの詳細は、MFC 拡張 DLL の記述方法を理解するうえでは重要ではありませんが、この実装を理解すると、独自の DLL を記述するのに役立ちます。

### <a name="implementation-overview"></a>実装の概要

MFC DLL は、既に説明したように、MFC 拡張 DLL の特殊なケースです。 多数のクラスに対して多数のエクスポートがあります。 MFC DLL には、通常の MFC 拡張 DLL よりも特殊な機能が追加されています。

### <a name="win32-does-most-of-the-work"></a>ほとんどの作業を Win32 で実行

16ビットバージョンの MFC では、スタックセグメント上のアプリごとのデータ、いくつかの80x86 アセンブリコードによって作成された特殊なセグメント、プロセスごとの例外コンテキスト、その他の手法など、さまざまな特殊な手法が必要でした。 Win32 は、DLL 内のプロセスごとのデータを直接サポートします。これは、ほとんどの場合に必要です。 ほとんどの部分 *`MFCxx.DLL`* は、 *`NAFXCW.LIB`* DLL にパッケージ化されています。 MFC のソースコードを見ると、いくつかのケースがあり `#ifdef _AFXDLL` ます。これは、いくつかの特殊なケースを作成する必要がないためです。 特に、Windows 3.1 (Win32s とも呼ばれます) で Win32 を処理する特殊なケースがあります。 Win32s は、プロセスごとの DLL データを直接サポートしていません。 MFC DLL では、プロセスローカルデータを取得するために、スレッドローカルストレージ (TLS) の Win32 Api を使用する必要があります。

### <a name="impact-on-library-sources-additional-files"></a>ライブラリソース、追加ファイルへの影響

`_AFXDLL`通常の MFC クラスライブラリのソースとヘッダーに対するバージョンの影響は、比較的軽微です。 特別なバージョンファイル ( *`AFXV_DLL.H`* ) と、 *`AFXDLL_.H`* メインヘッダーに含まれる追加のヘッダーファイル () があり *`AFXWIN.H`* ます。 ヘッダーには、 *`AFXDLL_.H`* `CDynLinkLibrary` `_AFXDLL` アプリケーションと MFC 拡張 dll のクラスおよびその他の実装の詳細が含まれています。 この *`AFXDLLX.H`* ヘッダーは、MFC 拡張 dll をビルドするために用意されています (詳細については、上記を参照してください)。

MFC SRC の MFC ライブラリに対する通常のソースには、#ifdef の下に追加の条件付きコードがいくつかあり `_AFXDLL` ます。 追加のソースファイル ( *`DLLINIT.CPP`* ) には、MFC の共有バージョン用の追加の DLL 初期化コードおよびその他のグルーが含まれています。

MFC の共有バージョンをビルドするために、追加のファイルが用意されています。 (DLL をビルドする方法の詳細については、以下を参照してください)。

- *`MFCxxD.DEF`* Dll の debug () および release () バージョンの MFC DLL エントリポイントをエクスポートするために、2つの DEF ファイルが使用されてい *`MFCxx.DEF`* ます。

- RC ファイル () には、 *`MFCDLL.RC`* すべての標準 MFC リソースと DLL のリソースが含まれてい `VERSIONINFO` ます。

- *`MFCDLL.CLW`* ClassWizard を使用して MFC クラスを参照できるようにするために、CLW ファイル () が用意されています。 この機能は、MFC の DLL バージョンに固有のものではありません。

### <a name="memory-management"></a>メモリ管理

を使用するアプリケーションは *`MFCxx.DLL`* 、共有の C ランタイム DLL によって提供される共通のメモリアロケーターを使用し *`MSVCRTxx.DLL`* ます。 アプリケーション、MFC 拡張 Dll、および MFC Dll は、この共有メモリアロケーターを使用します。 メモリ割り当てに共有 DLL を使用することにより、MFC Dll は、後でアプリケーションによって解放されるメモリまたはその逆のメモリを割り当てることができます。 アプリケーションと DLL の両方で同じアロケーターを使用する必要があるため、C++ グローバルまたはをオーバーライドしないで **`operator new`** **`operator delete`** ください。 その他の C ランタイムメモリ割り当てルーチン (、、など) にも同じ規則が適用され `malloc` `realloc` `free` ます。

### <a name="ordinals-and-class-__declspecdllexport-and-dll-naming"></a>序数およびクラス __declspec (dllexport) と DLL の名前付け

`class` **`__declspec(dllexport)`** C++ コンパイラの機能は使用しません。 代わりに、クラスライブラリソース (および) にエクスポートの一覧が含まれてい *`MFCxx.DEF`* *`MFCxxD.DEF`* ます。 エントリポイントの選択セット (関数とデータ) のみがエクスポートされます。 MFC プライベート実装関数やクラスなどの他のシンボルはエクスポートされません。 すべてのエクスポートは、組み込みまたは非常駐の名前テーブルに文字列名を指定せずに序数で実行されます。

を使用する `class` **`__declspec(dllexport)`** と、より小さな dll を構築するための代替手段となりますが、MFC のような大きな dll では、既定のエクスポートメカニズムに効率と容量の制限があります。

これは、実行や読み込みの速度を大幅に低下させずに、800 KB 程度の大量の機能をリリースにパッケージ化できることを意味 *`MFCxx.DLL`* します。 *`MFCxx.DLL`* この手法は使用されていないので、100 KB が大きくなります。 この手法を使用すると、DEF ファイルの末尾にエントリポイントを追加できます。 序数によるエクスポートの速度とサイズの効率を損なうことなく、単純なバージョン管理を行うことができます。 MFC クラスライブラリのメジャーバージョンのリビジョンによって、ライブラリ名が変更されます。 つまり、 *`MFC30.DLL`* は、MFC クラスライブラリのバージョン3.0 を含む再頒布可能な DLL です。 この DLL のアップグレード (たとえば、架空の MFC 3.1 では、DLL には代わりにという名前が付けら *`MFC31.DLL`* れます)。 ここでも、mfc のソースコードを変更して MFC DLL のカスタムバージョンを生成する場合は、別の名前を使用します (名前に "MFC" を付けないことをお勧めします)。

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
