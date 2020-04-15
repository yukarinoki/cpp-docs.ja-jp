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
ms.openlocfilehash: ad4cb883cfe7e397cf599d659afb02b23501dc5a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370311"
---
# <a name="tn033-dll-version-of-mfc"></a>テクニカル ノート 33: MFC の DLL バージョン

この資料では、MFC アプリケーションと MFC 拡張 DLL と共有ダイナミック リンク ライブラリ (mfc のバージョン番号は x) MFCxx.DLL と MFCxxD.DLL を使用する方法について説明します。 通常の MFC DLL の詳細については[、「MFC を DLL の一部として使用](../mfc/tn011-using-mfc-as-part-of-a-dll.md)する」を参照してください。

このテクニカル ノートは、DLL の 3 つの側面をカバーします。 最後の 2 つは、上級ユーザー向けです。

- [MFC 拡張 DLL のビルド方法](#_mfcnotes_how_to_write_an_mfc_extension_dll)

- [MFC の DLL バージョンを使用する MFC アプリケーションのビルド方法](#_mfcnotes_writing_an_application_that_uses_the_dll_version)

- [MFC 共有ダイナミック リンク ライブラリの実装方法](#_mfcnotes_how_the_mfc30.dll_is_implemented)

MFC 以外のアプリケーションで使用できる MFC を使用して DLL をビルドする場合 (これは通常の MFC DLL と呼ばれます)、[テクニカル ノート 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md)を参照してください。

## <a name="overview-of-mfcxxdll-support-terminology-and-files"></a>MFCxx.DLL のサポートの概要: 用語とファイル

**標準 MFC DLL**: MFC クラスの一部を使用してスタンドアロン DLL をビルドするには、通常の MFC DLL を使用します。 App/DLL 境界を越えたインターフェイスは "C" インターフェイスであり、クライアント アプリケーションは MFC アプリケーションである必要はありません。

MFC 1.0 でサポートされている DLL サポートのバージョンです。 テクニカル ノート[11](../mfc/tn011-using-mfc-as-part-of-a-dll.md)および MFC の高度な概念サンプル[DLLScreenCap](../overview/visual-cpp-samples.md)で説明します。

> [!NOTE]
> Visual C++ バージョン 4.0 では **、USRDLL**という用語は廃止され、MFC に静的にリンクする通常の MFC DLL に置き換えられています。 MFC に動的にリンクする通常の MFC DLL をビルドすることもできます。

MFC 3.0 (以上) は、OLE クラスやデータベース クラスを含むすべての新機能を備えた、標準 MFC DLL をサポートしています。

**AFXDLL**: MFC ライブラリの共有バージョンとも呼ばれます。 これは MFC 2.0 で追加された新しい DLL サポートです。 MFC ライブラリ自体は、いくつかの DLL (後述) に含まれ、クライアント アプリケーションまたは DLL は、必要な DLL を動的にリンクします。 アプリケーション/DLL 境界を越えたインターフェイスは、C++/MFC クラス インターフェイスです。 クライアント アプリケーションは MFC アプリケーションである必要があります。 この機能は、MFC 3.0 のすべての機能をサポートしています (ただし、データベース クラスでは UNICODE はサポートされていません)。

> [!NOTE]
> Visual C++ バージョン 4.0 では、この種類の DLL は "拡張 DLL" と呼ばれています。

このノートは、MFCxx.DLL を使用して、MFC DLL セット全体を参照します。

- デバッグ: MFCxxD.DLL (組み合わせ) と MFCSxxD.LIB (静的)。

- リリース: MFCxx.DLL (組み合わせ) と MFCSxx.LIB (静的)。

- ユニコード デバッグ: MFCxxUD.DLL (組み合わせ) と MFCSxxD.LIB (静的)。

- ユニコード リリース: MFCxxU.DLL (組み合わせ) と MFCSxxU.LIB (静的)。

> [!NOTE]
> MFCSxx[U][D]。LIB ライブラリは、MFC 共有 DLL と組み合わせて使用されます。 これらのライブラリには、アプリケーションまたは DLL に静的にリンクする必要があるコードが含まれています。

アプリケーションは、対応するインポート ライブラリにリンクします。

- デバッグ: MFCxxD.LIB

- リリース: MFCxx.LIB

- ユニコード デバッグ: MFCxxUD.LIB

- ユニコードリリース: MFCxxU.LIB

"MFC 拡張 DLL" は、MFCxx.DLL (および/または他の MFC 共有 DLL) 上に構築された DLL です。 ここでは、MFC コンポーネントのアーキテクチャが始まります。 MFC クラスから有用なクラスを派生させる場合、または MFC に似た別のツールキットをビルドする場合は、そのクラスを DLL に配置できます。 この DLL は、最終的なクライアント アプリケーションと同様に MFCxx.DLL を使用します。 これにより、再利用可能なリーフ クラス、再利用可能な基本クラス、および再利用可能なビュー/ドキュメント クラスが可能になります。

## <a name="pros-and-cons"></a>長所と短所

共有バージョンの MFC を使用する理由

- 共有ライブラリを使用すると、アプリケーションが小さくなる可能性があります (MFC ライブラリのほとんどを使用するアプリケーションは 10 K 未満です)。

- MFC の共有バージョンでは、MFC 拡張 DLL と通常の MFC DLL がサポートされています。

- MFC ライブラリをリンクする必要がないため、共有 MFC ライブラリを使用するアプリケーションのビルドは、静的にリンクされた MFC アプリケーションをビルドするよりも高速です。 これは、既にデバッグ情報を含む DLL とリンクすることで、デバッグ情報を圧縮する必要がある**DEBUG**ビルドでは特に当てはまります。

共有バージョンの MFC を使用しない理由

- 共有ライブラリを使用するアプリケーションを出荷するには、プログラムに MFCxx.DLL (およびその他) ライブラリを付属させる必要があります。 MFCxx.DLL は多くの DLL と同様に自由に再配布できますが、セットアップ プログラムに DLL をインストールする必要があります。 また、プログラムと MFC DLL 自体の両方で使用される C ランタイム ライブラリを含む MSVCRTxx.DLL を出荷する必要があります。

## <a name="how-to-write-an-mfc-extension-dll"></a><a name="_mfcnotes_how_to_write_an_mfc_extension_dll"></a>MFC 拡張 DLL を作成する方法

MFC 拡張 DLL は、MFC クラスの機能を装飾するために記述されたクラスと関数を含む DLL です。 MFC 拡張 DLL では、アプリケーションで使用するのと同じ方法で共有 MFC DLL を使用します。

- ビルド プロセスは、いくつかの追加のコンパイラ オプションとリンカー オプションを使用して、共有 MFC ライブラリを使用するアプリケーションをビルドするのと似ています。

- MFC 拡張 DLL には`CWinApp`、派生クラスがありません。

- MFC 拡張 DLL は、`DllMain`特別な . AppWizard には`DllMain`、ユーザーが変更できる関数が用意されています。

- MFC 拡張 DLL は通常、アプリケーションに es`CDynLinkLibrary`またはリソースをエクスポート`CRuntimeClass`する場合に、初期化ルーチンを提供して、 を作成します。 MFC 拡張`CDynLinkLibrary`DLL によってアプリケーションごとのデータを保持する必要がある場合は、 の派生クラスを使用できます。

これらの考慮事項については、以下で詳しく説明します。 MFC の高度な概念サンプル[DLLHUSK](../overview/visual-cpp-samples.md)も示しているので、参照してください。

- 共有ライブラリを使用してアプリケーションを構築する。 (DLLHUSK.EXE は、MFC ライブラリと他の DLL に動的にリンクする MFC アプリケーションです。

- MFC 拡張 DLL をビルドします。 (MFC 拡張 DLL`_AFXEXT`のビルドで使用されるような特別なフラグに注意してください)

- MFC 拡張 DLL の 2 つの例を示します。 1 つは、エクスポートが制限された MFC 拡張 DLL の基本構造を示し (TESTDLL1) とクラス インターフェイス全体のエクスポート (TESTDLL2) を示しています。

クライアント アプリケーションと MFC 拡張 DLL の両方で、同じバージョンの MFCxx.DLL を使用する必要があります。 MFC DLL の規則に従い、MFC 拡張 DLL のデバッグ バージョンと製品版 (/リリース) バージョンの両方を提供する必要があります。 これにより、クライアント プログラムは、アプリケーションのデバッグ バージョンと製品版の両方をビルドし、すべての DLL の適切なデバッグ バージョンまたは製品版とリンクできます。

> [!NOTE]
> C++ 名のマングルとエクスポートの問題のため、MFC 拡張 DLL からのエクスポート リストは、同じ DLL のデバッグ バージョンとリテール バージョン、およびプラットフォームごとに異なる DLL の間で異なる場合があります。 リテール MFCxx.DLL には、エクスポートされたエントリ ポイントが約 2000 個含まれています。デバッグ MFCxxD.DLL には、約 3000 のエクスポート エントリ ポイントがあります。

### <a name="quick-note-on-memory-management"></a>メモリ管理に関する簡単な注意事項

このテクニカル ノートの最後の「メモリ管理」では、MFC の共有バージョンを使用した MFCxx.DLL の実装について説明します。 MFC 拡張 DLL を実装するために知っておくべきことは、ここで説明します。

MFCxx.DLL とクライアント アプリケーションのアドレス空間に読み込まれるすべての MFC 拡張 DLL は、同じアプリケーションにあるかのように、同じメモリ アロケーター、リソースの読み込み、およびその他の MFC の "グローバル" 状態を使用します。 MFC に静的にリンクする非 MFC DLL ライブラリと通常の MFC DLL は、正反対の処理を行い、各 DLL が独自のメモリ プールから割り当てできるため、これは重要です。

MFC 拡張 DLL がメモリを割り当てる場合、そのメモリは、アプリケーションが割り当てた他のオブジェクトと自由に混在できます。 また、共有 MFC ライブラリを使用するアプリケーションがクラッシュした場合、オペレーティング システムの保護によって、DLL を共有する他の MFC アプリケーションの整合性が維持されます。

同様に、リソースを読み込む現在の実行可能ファイルのような他の "グローバル" MFC の状態も、クライアント アプリケーションとすべての MFC 拡張 DLL と MFCxx.DLL 自体の間で共有されます。

### <a name="building-an-mfc-extension-dll"></a>MFC 拡張 DLL のビルド

AppWizard を使用して MFC 拡張 DLL プロジェクトを作成すると、適切なコンパイラ設定とリンカ設定が自動的に生成されます。 また、変更できる`DllMain`関数も生成されました。

既存のプロジェクトを MFC 拡張 DLL に変換する場合は、まず、MFC の共有バージョンを使用してアプリケーションをビルドするための標準規則から始めて、次の操作を行います。

- コンパイラ フラグに **/D_AFXEXT**を追加します。 [プロジェクトプロパティ]ダイアログで、C/C++ノードを選択します。 次に、プリプロセッサカテゴリを選択します。 [`_AFXEXT`マクロの定義] フィールドに、各項目をセミコロンで区切って追加します。

- **/Gy**コンパイラ スイッチを削除します。 [プロジェクトプロパティ]ダイアログで、C/C++ノードを選択します。 次に、[コード生成] カテゴリを選択します。 [機能レベルのリンクを有効にする] オプションが有効になっていないことを確認します。 これにより、リンカーは参照されていない関数を削除しないため、クラスをエクスポートしやすくなります。 元のプロジェクトを使用して MFC に静的にリンクされた標準 MFC DLL をビルドする場合は **、/MT[d]** コンパイラ オプションを **/MD[d]** に変更します。

- LINK に **/DLL**オプションを指定してエクスポート ライブラリをビルドします。 これは、新しいターゲットを作成するときに設定され、ターゲットの種類として Win32 ダイナミック リンク ライブラリを指定します。

### <a name="changing-your-header-files"></a>ヘッダー ファイルの変更

MFC 拡張 DLL の目的は、通常、その機能を使用できる 1 つ以上のアプリケーションに一般的な機能をエクスポートすることです。 これは、クライアント アプリケーションで使用できるクラスとグローバル関数をエクスポートする方法です。

これを行うには、各メンバー関数が適切にインポートまたはエクスポートとしてマークされていることを確認する必要があります。 これには、特別な宣言と`__declspec(dllexport)``__declspec(dllimport)`. クライアント アプリケーションでクラスを使用する場合は、 として`__declspec(dllimport)`宣言する必要があります。 MFC 拡張 DLL 自体がビルドされるとき、それらは`__declspec(dllexport)`. また、クライアント プログラムが読み込み時にバインドされるように、関数を実際にエクスポートする必要があります。

クラス全体をエクスポートするには、クラス`AFX_EXT_CLASS`定義で使用します。 このマクロは、フレームワークによって定義された`__declspec(dllexport)`場合`_AFXDLL`と`_AFXEXT`定義されている場合として定義されますが`__declspec(dllimport)`、`_AFXEXT`定義されていない場合として定義されます。 `_AFXEXT`上記のように、MFC 拡張 DLL をビルドする場合にのみ定義されます。 次に例を示します。

```cpp
class AFX_EXT_CLASS CExampleExport : public CObject
{ /* ... class definition ... */ };
```

### <a name="not-exporting-the-entire-class"></a>クラス全体をエクスポートしない

必要な個々のクラスのメンバーだけをエクスポートしたい場合があります。 たとえば、派生クラスを`CDialog`エクスポートする場合は、コンストラクターと`DoModal`呼び出しのみをエクスポートする必要があります。 これらのメンバーは、DLL の を使用してエクスポートできます。DEF ファイルですが、エクスポートする必要`AFX_EXT_CLASS`がある個々のメンバーで使用することもできます。

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

この操作を行うと、クラスのすべてのメンバーをエクスポートしなくなったため、追加の問題が発生する可能性があります。 問題は MFC マクロの動作方法にあります。 MFC のヘルパー マクロのいくつかは、実際にはデータ メンバーを宣言または定義します。 したがって、これらのデータ メンバーも DLL からエクスポートする必要があります。

たとえば、MFC 拡張 DLL をビルドする場合、DECLARE_DYNAMIC マクロは次のように定義されます。

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
    static CRuntimeClass* PASCAL _GetBaseClass(); \
    public: \
    static AFX_DATA CRuntimeClass class##class_name; \
    virtual CRuntimeClass* GetRuntimeClass() const; \
```

"static"`AFX_DATA`を始める行は、クラス内で静的オブジェクトを宣言しています。 このクラスを正しくエクスポートし、クライアントからランタイム情報にアクセスするには、EXE を実行するには、この静的オブジェクトをエクスポートする必要があります。 静的オブジェクトは`AFX_DATA`修飾子 で宣言されるため、DLL をビルドするときに定義`AFX_DATA``__declspec(dllexport)`し、クライアント実行可能ファイルをビルドするときにそれを定義`__declspec(dllimport)`する必要があります。

上記で説明したように、`AFX_EXT_CLASS`既にこのように定義されています。 クラス定義の`AFX_EXT_CLASS`周囲と同じ`AFX_DATA`に再定義する必要があります。

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

MFC は、`AFX_DATA`マクロ内で定義するデータ項目に常にシンボルを使用するため、この手法はこのようなすべてのシナリオで機能します。 たとえば、DECLARE_MESSAGE_MAPのために動作します。

> [!NOTE]
> クラスの選択されたメンバーではなく、クラス全体をエクスポートする場合、静的データ メンバーは自動的にエクスポートされます。

DECLARE_SERIALとIMPLEMENT_SERIALマクロを使用するクラスの抽出`CArchive`演算子を自動的にエクスポートする場合も、同じ方法を使用できます。 クラス宣言 ( 内の ) をかっこで囲んでアーカイブ演算子をエクスポートします。H ファイル) と次のコード:

```cpp
#undef AFX_API
#define AFX_API AFX_EXT_CLASS

/* your class declarations here */

#undef AFX_API
#define AFX_API
```

### <a name="limitations-of-_afxext"></a>_AFXEXTの制限事項

MFC 拡張 DLL の複数のレイヤーがない限り、MFC 拡張 DLL に _**AFXEXT**プリプロセッサ シンボルを使用できます。 MFC 拡張 DLL を呼び出すか、MFC クラスから派生する MFC 拡張 DLL がある場合は、あいまいさを避けるために、独自のプリプロセッサ シンボルを使用する必要があります。

問題は、Win32 では、DLL からエクスポートする場合と、DLL からインポートする場合と`__declspec(dllexport)``__declspec(dllimport)`同様に、データを明示的に宣言する必要がある点です。 を定義`_AFXEXT`する際に、MFC ヘッダーが正`AFX_EXT_CLASS`しく定義されていることを確認します。

複数のレイヤーがある場合、MFC 拡張`AFX_EXT_CLASS`DLL が新しいクラスをエクスポートし、別の MFC 拡張 DLL から他のクラスをインポートする可能性があるため、シンボルが 1 つでは不十分です。 この問題に対処するには、DLL 自体をビルドしようとしていることを示す特別なプリプロセッサ シンボルを使用します。 たとえば、2 つの MFC 拡張 DLL、A.DLL、および B.DLL を考えてみましょう。 それぞれ A.H と B.H でいくつかのクラスをエクスポートします。 B.DLL は A.DLL のクラスを使用します。 ヘッダー ファイルは次のようになります。

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

A.DLL がビルドされると **、/DA_IMPL**でビルドされ、B.DLL がビルドされると **/DB_IMPL**でビルドされます。 各 DLL に対して個別のシンボルを使用することにより、CExampleB がエクスポートされ、B.DLL をビルドするときに CExampleA がインポートされます。 CExampleA は A.DLL をビルドするときにエクスポートされ、B.DLL (または他のクライアント) で使用されるときにインポートされます。

組み込みシンボルと`AFX_EXT_CLASS``_AFXEXT`プリプロセッサ シンボルを使用する場合、このタイプのレイヤ化は行えません。 上記の手法では、MFC 自体が OLE、データベース、およびネットワーク MFC 拡張機能 DLL をビルドするときに使用するメカニズムと異なり、この問題を解決します。

### <a name="not-exporting-the-entire-class"></a>クラス全体をエクスポートしない

繰り返しますが、クラス全体をエクスポートしない場合は、特別な注意が必要です。 MFC マクロによって作成された必要なデータ項目が正しくエクスポートされるようにする必要があります。 これは、特定のクラスのマクロを`AFX_DATA`再定義することによって行うことができます。 これは、クラス全体をエクスポートしない場合はいつでも行う必要があります。

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

次に示しているのは、MFC 拡張 DLL のメイン ソース ファイルに配置する必要がある正確なコードです。 これは、標準が含まれている後に来る必要があります。 AppWizard を使用して MFC 拡張 DLL のスタート ファイルを作成すると`DllMain`、A が提供されます。

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

モジュールのランタイム`AfxInitExtensionModule`クラス (構造体) とその`CRuntimeClass`オブジェクト ファクトリ (`COleObjectFactory`オブジェクト) をキャプチャする呼び出しは、`CDynLinkLibrary`オブジェクトの作成時に後で使用します。 (省略可能) 呼`AfxTermExtensionModule`び出しを使用すると、MFC 拡張 DLL から各プロセスがデタッチ (プロセスが終了したとき、または`FreeLibrary`呼び出しの結果として DLL がアンロードされるときに発生する) 場合に MFC 拡張 DLL をクリーンアップできます。 ほとんどの MFC 拡張 DLL は動的に読み込まれていないため (通常はインポート ライブラリを介`AfxTermExtensionModule`してリンクされます)、呼び出しは通常必要ありません。

アプリケーションで MFC 拡張 DLL を動的に読み込んで解放する`AfxTermExtensionModule`場合は、上記のように必ず呼び出してください。 また、アプリケーションが複数`AfxLoadLibrary`の`AfxFreeLibrary`スレッドを使用する場合や`LoadLibrary`MFC`FreeLibrary`拡張 DLL を動的に読み込む場合は、Win32 関数および () の代わりに、 と を使用してください。 MFC 拡張 DLL が読み込まれ、アンロードされたときに実行されるスタートアップ コードとシャットダウン コードを使用`AfxLoadLibrary`して保証します。 `AfxFreeLibrary`

ヘッダー ファイル AFXDLLX。H には、MFC 拡張 DLL で使用される構造体の特殊な定義`AFX_EXTENSION_MODULE`が含`CDynLinkLibrary`まれています。

グローバル*拡張 DLL*は、次のように宣言する必要があります。 16 ビットバージョンの MFC とは異なり、この間は、MFCxx.DLL が呼び出された時点`DllMain`で完全に初期化されるため、この間にメモリを割り当てて MFC 関数を呼び出すことができます。

### <a name="sharing-resources-and-classes"></a>リソースやクラスの共有

単純な MFC 拡張 DLL は、少数の低帯域幅関数をクライアント アプリケーションにエクスポートするだけで、それ以上は何もエクスポートする必要はありません。 ユーザー インターフェイスを集中的に使用する DLL の方が、リソースと C++ クラスをクライアント アプリケーションにエクスポートする必要が生じる場合があります。

リソースのエクスポートには、リソース リストを使います。 各アプリケーションでは、オブジェクトの一連の`CDynLinkLibrary`リンクリストです。 リソースを検索する場合、リソースを読み込む標準 MFC の実装のほとんどは、まず現在のリソース`AfxGetResourceHandle`モジュール ( ) を参照`CDynLinkLibrary`し、見つからなかった場合は、要求されたリソースを読み込もうとしているオブジェクトの一覧を参照します。

C++ クラス名を指定した C++ オブジェクトの動的な作成は似ています。 MFC オブジェクトの逆シリアル化機構では、以前に`CRuntimeClass`格納されていたものに基づいて必要な型の C++ オブジェクトを動的に作成して再構築できるように、すべてのオブジェクトを登録する必要があります。

クライアント アプリケーションで MFC 拡張 DLL のクラスを使用する`DECLARE_SERIAL`場合は、クライアント アプリケーションから参照できるクラスをエクスポートする必要があります。 これはリストを歩くこと`CDynLinkLibrary`でも行われます。

MFC の高度な概念サンプル[DLLHUSK](../overview/visual-cpp-samples.md)の場合、リストは次のようになります。

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

MFCxx.DLL は、通常、リソースとクラスの一覧の最後に表示されます。 MFCxx.DLL には、標準のコマンド ID のプロンプト文字列を含む、すべての標準 MFC リソースが含まれています。 このリストを一覧の末尾に配置すると、DLL とクライアント アプリケーション自体は、標準 MFC リソースの独自のコピーを持たないが、MFCxx.DLL の共有リソースに依存できます。

すべての DLL のリソースとクラス名をクライアント アプリケーションのネーム スペースにマージする場合、ID や名前を指定する際には注意が必要であるという欠点があります。 もちろん、リソースまたはオブジェクトをクライアント アプリケーションにエクスポートしないことで、`CDynLinkLibrary`この機能を無効にできます。 [DLLHUSK](../overview/visual-cpp-samples.md)サンプルでは、複数のヘッダー ファイルを使用して共有リソースのネームスペースを管理します。 共有リソース ファイルの使用に関するヒントについては、[テクニカル ノート 35](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)を参照してください。

### <a name="initializing-the-dll"></a>DLL の初期化

前述のように、通常は、リソースとクラスを`CDynLinkLibrary`クライアント アプリケーションにエクスポートするためにオブジェクトを作成します。 DLL を初期化するには、エクスポートされたエントリ ポイントを指定する必要があります。 最小限に、これは引数を取らず、何も返さないvoidルーチンですが、好きなものは何でもできます。

この方法を使用する場合は、DLL を使用する各クライアント アプリケーションでこの初期化ルーチンを呼び出す必要があります。 この`CDynLinkLibrary`オブジェクトは、 を呼び`DllMain`出した`AfxInitExtensionModule`直後に割り当てることもできます。

初期化ルーチンは、MFC`CDynLinkLibrary`拡張 DLL 情報に接続された、現在のアプリケーションのヒープ内にオブジェクトを作成する必要があります。 これは、次の方法で実行できます。

```cpp
extern "C" extern void WINAPI InitXxxDLL()
{
    new CDynLinkLibrary(extensionDLL);
}
```

この例では、ルーチン名*InitXxxDLL*は、必要な値を指定できます。 **extern "C"** である必要はありませんが、エクスポートリストの保守が容易になります。

> [!NOTE]
> 通常の MFC DLL から MFC 拡張 DLL を使用する場合は、この初期化関数をエクスポートする必要があります。 この関数は、MFC 拡張 DLL のクラスまたはリソースを使用する前に、通常の MFC DLL から呼び出す必要があります。

### <a name="exporting-entries"></a>エントリのエクスポート

クラスをエクスポートする簡単な方法は、エクスポート`__declspec(dllimport)`する`__declspec(dllexport)`各クラスとグローバル関数を使用することです。 これにより、エクスポートする関数の制御が少なく、関数を序数でエクスポートできないため、各エントリ ポイント (以下で説明) に名前を付けるよりも効率が悪くなります。 TESTDLL1 および TESTDLL2 は、このメソッドを使用してエントリをエクスポートします。

より効率的な方法 (および MFCxx.DLL で使用されるメソッド) では、 の各エントリに名前を付けて各エントリを手入力でエクスポートします。DEF ファイル。 DLL から選択的なエクスポートをエクスポートしているので (すべてではない)、エクスポートする特定のインターフェイスを決定する必要があります。 これは、タングルされた名前をリンカーに対して、 のエントリの形式で指定する必要があるため、困難です。DEF ファイル。 C++ クラスのシンボリック リンクが本当に必要な場合を除き、C++ クラスをエクスポートしないでください。

を使用して C++ クラスをエクスポートしようとした場合DEF ファイルを作成する前に、このリストを自動的に生成するツールを開発する必要があります。 これは、2 段階のリンク プロセスを使用して行うことができます。 エクスポートなしで DLL を 1 回リンクし、リンカーが .MAP ファイル。 .MAP ファイルを使用してエクスポートする必要のある関数のリストを生成できるため、一部の並べ替えで、 の EXPORT エントリを生成するために使用できます。DEF ファイル。 MFCxx.DLL および OLE およびデータベース MFC 拡張 DLL のエクスポートリストは、数千個の数のプロセスで生成されました (ただし、完全に自動ではなく、時々手のチューニングが必要です)。

### <a name="cwinapp-vs-cdynlinklibrary"></a>CWinApp vs. CDynLinkライブラリ

MFC 拡張 DLL には、`CWinApp`独自の派生オブジェクトがありません。代わりに、クライアント アプリケーション`CWinApp`の -derived オブジェクトを使用する必要があります。 これは、クライアント アプリケーションがメイン メッセージ ポンプ、アイドル ループなどを所有していることを意味します。

MFC 拡張 DLL がアプリケーションごとに余分なデータを保持する必要がある場合は、新`CDynLinkLibrary`しいクラスを派生し、上記の InitXxxDLL ルーチンで作成できます。 実行中、DLL は、現在のアプリケーションのオブジェクトのリストを`CDynLinkLibrary`チェックして、その特定の MFC 拡張 DLL のオブジェクトを見つけることができます。

### <a name="using-resources-in-your-dll-implementation"></a>DLL 実装でのリソースの使用

前述のように、既定のリソースの読み込みは、要求`CDynLinkLibrary`されたリソースを持つ最初の EXE または DLL を探しているオブジェクトの一覧を参照します。 すべての MFC API とすべての内部コードは、`AfxFindResourceHandle`リソースリストをウォークしてリソースを検索するために使用します。

特定の場所からのリソースだけをロードする場合は、API を`AfxGetResourceHandle`使用して`AfxSetResourceHandle`古いハンドルを保存し、新しいハンドルを設定します。 クライアント アプリケーションに戻る前に、元のリソース ハンドルを必ず復元してください。 サンプル TESTDLL2 では、この方法を使用してメニューを明示的に読み込んでいます。

リストを検索する場合、多少速度が低下することとリソース ID 範囲の管理が必要なことが欠点です。 いくつかの MFC 拡張 DLL にリンクするクライアント アプリケーションでは、DLL インスタンス ハンドルを指定しなくても DLL によって提供されるリソースを使用できるという利点があります。 `AfxFindResourceHandle` は、リソース リストを検索して一致するリソースを見つけるのに使われる API です。 リソースの名前と型を受け取り、最初に一致したリソース ハンドル (または NULL) を返します。

## <a name="writing-an-application-that-uses-the-dll-version"></a><a name="_mfcnotes_writing_an_application_that_uses_the_dll_version"></a>DLL バージョンを使用するアプリケーションの作成

### <a name="application-requirements"></a>アプリケーション要件

MFC の共有バージョンを使用するアプリケーションは、いくつかの簡単な規則に従う必要があります。

- オブジェクトを`CWinApp`持ち、メッセージ ポンプの標準規則に従う必要があります。

- 必要なコンパイラ フラグのセットを使用してコンパイルする必要があります (下記参照)。

- MFCxx インポート ライブラリとリンクする必要があります。 必要なコンパイラ フラグを設定することにより、MFC ヘッダーは、アプリケーションがリンクするライブラリをリンク時に決定します。

- 実行可能ファイルを実行するには、MFCxx.DLL がパス上または Windows システム ディレクトリに存在する必要があります。

### <a name="building-with-the-development-environment"></a>開発環境を用いて構築

標準の標準の大部分を使用して内部メイクファイルを使用している場合は、簡単にプロジェクトを変更して DLL バージョンをビルドできます。

次の手順では、正常に機能している MFC アプリケーションが NAFXCWD にリンクされていることを前提としています。LIB (デバッグ用) と NAFXCW。LIB (製品版用) を使用して、MFC ライブラリの共有バージョンを使用するように変換します。 Visual C++ 環境を実行しており、内部プロジェクト ファイルを使用している場合。

1. [**プロジェクト**] メニューの [**プロパティ**] をクリックします。 [**プロジェクトの既定値]** の [**全般**] ページで **、[MFC**を共有 DLL (MFCxx(d).dll) で使用する Microsoft ファウンデーション クラス] を設定します。

### <a name="building-with-nmake"></a>NMAKE を使用した建物

Visual C++ の外部メイクファイル機能を使用している場合、または NMAKE を直接使用している場合は、メイクファイルを編集してコンパイラとリンカーのオプションをサポートする必要があります。

必要なコンパイラ フラグ:

- **/D_AFXDLL /MD**
   **/D_AFXDLL**

標準 MFC ヘッダーでは、次の記号を定義する必要があります。

- **/MD**アプリケーションは、C ランタイム ライブラリの DLL バージョンを使用する必要があります。

その他のコンパイラ フラグはすべて、MFC の既定値に従います (デバッグの場合は_DEBUGなど)。

ライブラリのリンカ リストを編集します。 NAFXCWD を変更します。LIB を MFCxxD.LIB に変換し、NAFXCW を変更します。を MFCxx.LIB に変換します。 LIBC を交換してください。MSVCRT を使用した LIB。Lib。 他の MFC ライブラリと同様に、MFCxxD.LIB は C ランタイム ライブラリの**前に**配置することが重要です。

必要に応じて、リテール リソースとデバッグ リソースの両方のコンパイラ オプション **(/R**を使用してリソースをコンパイルするオプション) の両方に **/D_AFXDLL**を追加します。 これにより、MFC DLL に存在するリソースを共有することで、最終的な実行可能ファイルが小さくなります。

これらの変更が行われた後は、完全な再構築が必要です。

### <a name="building-the-samples"></a>サンプルのビルド

MFC サンプル プログラムのほとんどは、Visual C++ からビルドすることも、コマンド ラインから NMAKE と互換性のある共有 MAKEFILE からビルドすることもできます。

これらのサンプルを変換して MFCxx.DLL を使用するには、 をロードします。MAK ファイルを Visual C++ に変換し、上記の手順でプロジェクト オプションを設定します。 NMAKE ビルドを使用している場合は、NMAKE コマンド ラインで "AFXDLL=1" を指定でき、共有 MFC ライブラリを使用してサンプルをビルドします。

MFC の高度な概念サンプル[DLLHUSK](../overview/visual-cpp-samples.md)は、MFC の DLL バージョンでビルドされています。 このサンプルでは、MFCxx.DLL にリンクされたアプリケーションをビルドする方法を示すだけでなく、このテクニカル ノートで後述する MFC 拡張 DLL などの MFC DLL パッケージ オプションの他の機能も示します。

### <a name="packaging-notes"></a>パッケージングノート

DLL の製品版 (MFCxx[U])。DLL) は自由に再頒布可能です。 DLL のデバッグ バージョンは自由に再頒布可能なものではなく、アプリケーションの開発中にのみ使用する必要があります。

デバッグ DLL には、デバッグ情報が用意されています。 Visual C++ デバッガーを使用すると、アプリケーションの実行と DLL の実行をトレースできます。 リリース DLL (MFCxx[U])。DLL) にはデバッグ情報が含まれていません。

DLL をカスタマイズまたは再構築する場合は、MFC SRC ファイル MFCDLL を "MFCxx" 以外の名前で呼び出す必要があります。MAK では、ビルド オプションについて説明し、DLL の名前を変更するためのロジックを含んでいます。 これらの DLL は多くの MFC アプリケーションで共有される可能性があるため、ファイルの名前を変更する必要があります。 カスタム バージョンの MFC DLL がシステムにインストールされている DLL に置き換わる場合、共有 MFC DLL を使用して別の MFC アプリケーションが壊れる可能性があります。

MFC DLL の再構築はお勧めしません。

## <a name="how-the-mfcxxdll-is-implemented"></a><a name="_mfcnotes_how_the_mfc30.dll_is_implemented"></a>MFCxx.DLL の実装方法

次のセクションでは、MFC DLL (MFCxx.DLL および MFCxxD.DLL) の実装方法について説明します。 アプリケーションで MFC DLL を使用する場合は、ここで説明する内容を理解することは重要ではありません。 MFC 拡張 DLL の記述方法を理解するためには、ここでの詳細は必須ではありませんが、この実装を理解することは、独自の DLL を記述するのに役立ちます。

### <a name="implementation-overview"></a>実装の概要

MFC DLL は、上記の MFC 拡張 DLL の特殊なケースです。 多数のクラスに対して非常に多くのエクスポートがあります。 MFC DLL では、通常の MFC 拡張 DLL よりもさらに特殊な機能を持つ追加の操作がいくつかあります。

### <a name="win32-does-most-of-the-work"></a>Win32 はほとんどの作業を行います

MFC の 16 ビット バージョンでは、スタック セグメント上のアプリごとのデータ、一部の 80x86 アセンブリ コードによって作成された特殊なセグメント、プロセスごとの例外コンテキスト、およびその他の手法など、多くの特殊な手法が必要でした。 Win32 は、DLL 内のプロセスごとのデータを直接サポートします。 ほとんどの場合、MFCxx.DLL は単なる NAFXCW です。DLL にパッケージ化された LIB。 MFC ソース コードを見ると、特別なケースが非常に少ないため、_AFXDLL#ifdefはほとんどありません。 Windows 3.1 (Win32s) で Win32 を扱う特別なケースがあります。 Win32s はプロセスごとの DLL データを直接サポートしていないため、MFC DLL はスレッド ローカル ストレージ (TLS) Win32 API を使用してプロセスローカル データを取得する必要があります。

### <a name="impact-on-library-sources-additional-files"></a>ライブラリ ソース、追加ファイルへの影響

通常の MFC クラス ライブラリのソースとヘッダーに対する **_AFXDLL**バージョンの影響は比較的小さいものです。 特殊なバージョン ファイル (AFXV_DLLがあります。H) と追加のヘッダー ファイル (AFXDLL_。H)メインAFXWINによって含まれています。H ヘッダー。 AFXDLL_。H ヘッダーには`CDynLinkLibrary`、アプリケーションと MFC 拡張`_AFXDLL`DLL の両方のクラスとその他の実装の詳細が含まれています。 The AFXDLLX.H ヘッダーは、MFC 拡張 DLL をビルドするために用意されています (詳細については、上記を参照してください)。

MFC SRC の MFC ライブラリへの通常のソースには、#ifdefの`_AFXDLL`下にいくつかの追加の条件コードがあります。 追加のソース ファイル (DLLINIT.CPP) には、MFC の共有バージョン用の追加の DLL 初期化コードと他の接着が含まれています。

MFC の共有バージョンをビルドするために、追加のファイルが提供されます。 (DLL のビルド方法の詳細については、以下を参照してください。

- 2 .DEF ファイルは、デバッグ (MFCxxD.DEF) およびリリース (MFCxx.DEF) バージョンの DLL の MFC DLL エントリ ポイントをエクスポートするために使用されます。

- .RC ファイル (MFCDLL.RC) には、すべての標準 MFC リソースと、DLL の VERSIONINFO リソースが含まれています。

- A。CLW ファイル (MFCDLL.CLW) は、クラス ウィザードを使用して MFC クラスを参照できるようにするために提供されています。 注意 : この機能は、MFC の DLL バージョンに固有の機能ではありません。

### <a name="memory-management"></a>メモリ管理

MFCxx.DLL を使用するアプリケーションは、共有 C ランタイム DLL である MSVCRTxx.DLL によって提供される共通メモリ アロケーターを使用します。 アプリケーション、MFC 拡張 DLL、および MFC DLL 自体は、この共有メモリ アロケーターを使用します。 メモリ割り当てに共有 DLL を使用すると、MFC DLL は、後でアプリケーションによって解放されるメモリを割り当てることができます。 アプリケーションと DLL の両方で同じアロケーターを使用する必要があるため、C++ グローバル**演算子 new**または**operator delete**をオーバーライドしないでください。 C ランタイム メモリ割り当てルーチン **(malloc**、 **realloc**、 **free**など ) の残りの部分にも同じ規則が適用されます。

### <a name="ordinals-and-class-__declspecdllexport-and-dll-naming"></a>序数、クラス __declspec(dllexport)、および DLL の名前付け

C++ コンパイラの`class`**__declspec (dllexport)** 機能は使用しません。 代わりに、エクスポートのリストがクラス ライブラリ ソース (MFCxx.DEF および MFCxxD.DEF) に含まれます。 これらの選択したエントリ ポイント (関数とデータ) のみがエクスポートされます。 MFC プライベート実装関数やクラスなどの他のシンボルはエクスポートされません すべてのエクスポートは、常駐または常駐名テーブルに文字列名を付けずに序数で行われます。

`class` **__declspec(dllexport) を**使用すると、小さな DLL を構築する場合に有効な方法ですが、MFC のような大きな DLL の場合、既定のエクスポートメカニズムには効率と容量の制限があります。

この意味は、多くの実行速度や読み込み速度を損なうことなく、約 800 KB のリリース MFCxx.DLL に大量の機能をパッケージ化できることです。 この手法が使用されなければ、MFCxx.DLL は 100K 大きかったでしょう。 これにより、 の末尾にエントリ ポイントを追加することもできます。DEFファイルは、序数によるエクスポートの速度とサイズ効率を損なうことなく簡単なバージョン管理を可能にします。 MFC クラス ライブラリのメジャー バージョンのリビジョンによって、ライブラリ名が変更されます。 つまり、MFC30 です。DLL は、MFC クラス ライブラリのバージョン 3.0 を含む再頒布可能 DLL です。 たとえば、この DLL のアップグレードは、たとえば、仮想 MFC 3.1 では、MFC31 という名前になります。代わりに DLL。 ここでも、MFC のソース コードを変更して MFC DLL のカスタム バージョンを生成する場合は、別の名前 (名前に "MFC" を含まない名前を使用する場合) を使用します。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
