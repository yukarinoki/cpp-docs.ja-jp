---
title: 'TN033: MFC の DLL バージョン |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.dll
dev_langs:
- C++
helpviewer_keywords:
- MFC DLLs [MFC], writing MFC extension DLLS
- AFXDLL library
- DLLs [MFC], MFC
- DLL version of MFC [MFC]
- TN033
ms.assetid: b6f1080b-b66b-4b1e-8fb1-926c5816392c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a247ffc36b3e0eb3e52c6f04949c693597d73064
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385243"
---
# <a name="tn033-dll-version-of-mfc"></a>テクニカル ノート 33: MFC の DLL バージョン
ここでは、MFCxx.DLL を使用することができ、MFCxxD.DLL (x は MFC のバージョン番号) は、MFC アプリケーションおよび MFC 拡張 Dll とダイナミック リンク ライブラリを共有する方法について説明します。 正規の MFC Dll の詳細については、次を参照してください。 [DLL の一部としての MFC](../mfc/tn011-using-mfc-as-part-of-a-dll.md)です。  
  
 このテクニカル ノートでは、Dll の 3 つの側面について説明します。 最後の 2 つより上級のユーザーのことです。  
  
- [MFC 拡張 DLL をビルドする方法](#_mfcnotes_how_to_write_an_mfc_extension_dll)  
  
- [MFC の DLL バージョンを使用する MFC アプリケーションを構築する方法](#_mfcnotes_writing_an_application_that_uses_the_dll_version)  
  
- [実装は、MFC でのダイナミック リンク ライブラリを共有する方法](#_mfcnotes_how_the_mfc30.dll_is_implemented)  
  
 (標準 MFC DLL と呼ばれます) の非 MFC アプリケーションで使用できる MFC を使用する DLL のビルドする場合を参照してください。[テクニカル ノート 11:](../mfc/tn011-using-mfc-as-part-of-a-dll.md)です。  
  
## <a name="overview-of-mfcxxdll-support-terminology-and-files"></a>MFCxx.DLL サポートの概要: 用語とファイル  
 **正規の MFC DLL**: 標準 MFC DLL を使用して、一部の MFC クラスを使用してスタンドアロンの DLL をビルドします。 アプリ/DLL の境界を越えてインターフェイスは、"C"インターフェイスと、クライアント アプリケーションは MFC アプリケーションする必要はありません。  
  
 これは、MFC 1.0 でサポートされている DLL のサポートのバージョンです。 説明されている、[テクニカル ノート 11:](../mfc/tn011-using-mfc-as-part-of-a-dll.md)と MFC Advanced Concepts サンプル[は](../visual-cpp-samples.md)します。  
  
> [!NOTE]
>  Visual C のバージョン 4.0 の時点で、用語**USRDLL**は廃止され、MFC と静的にリンクされるレギュラー MFC DLL から置き換えです。 また、標準 MFC と動的にリンクする MFC DLL をビルドする可能性があります。  
  
 MFC 3.0 (以降)、OLE、およびデータベース クラスを含むすべての新機能に標準の MFC Dll をサポートしています。  
  
 **AFXDLL**: これとも呼びます MFC ライブラリの共有バージョン。 これは、MFC 2.0 で追加された新しい DLL サポートです。 MFC ライブラリ自体は、多くの Dll (後述) であり、必要な Dll が動的にリンク、クライアント アプリケーションまたは DLL。 アプリケーション/DLL の境界を越えてインターフェイスは、C + + MFC クラスのインターフェイスです。 クライアント アプリケーションは、MFC アプリケーションである必要があります。 すべての MFC 3.0 の機能がサポートされます (例外: データベース クラス用 UNICODE がサポートされていません)。  
  
> [!NOTE]
>  Visual C バージョン 4.0 の時点でこの種類の DLL と呼びます「拡張 DLL です」  
  
 この注意を MFCxx.DLL を使用して、MFC の DLL は、次の設定、全体が含まれるを参照してください。  
  
-   デバッグ: MFCxxD.DLL (組み合わせ) と MFCSxxD.LIB (静的)。  
  
-   リリース: (結合) MFCxx.DLL や MFCSxx.LIB (静的)。  
  
-   Unicode のデバッグ: MFCxxUD.DLL (組み合わせ) と MFCSxxD.LIB (静的)。  
  
-   Unicode リリース: MFCxxU.DLL (組み合わせ) と MFCSxxU.LIB (静的)。  
  
> [!NOTE]
>  MFCSxx [U] [D] です。LIB ライブラリで使用されると共に、MFC Dll を共有します。 これらのライブラリには、アプリケーションまたは DLL に静的にリンクする必要がありますコードが含まれています。  
  
 対応する、アプリケーションへのリンクは、ライブラリをインポートします。  
  
-   デバッグ: MFCxxD.LIB  
  
-   リリース: MFCxx.LIB  
  
-   Unicode のデバッグ: MFCxxUD.LIB  
  
-   Unicode リリース: MFCxxU.LIB  
  
 "MFC 拡張 DLL"は MFCxx.DLL に基づいて構築されている DLL (またはその他の MFC 共有 Dll) です。 ここは、MFC コンポーネントのアーキテクチャが開始されます。 MFC クラスからクラスを派生させるか、別の MFC のようなツールキットをビルドした場合は、DLL に配置することができます。 最終的なクライアント アプリケーションでは、DLL として MFCxx.DLL を使用します。 これにより、再利用可能なリーフ クラス、再利用可能な基本クラス、および再利用可能なビュー/ドキュメント クラスです。  
  
## <a name="pros-and-cons"></a>長所と短所  
 使用する理由、MFC の共有バージョン  
  
-   共有ライブラリを使用すると、小規模なアプリケーションが (MFC ライブラリのほとんどを使用する最低限のアプリケーションは 10 K 未満) があります。  
  
-   MFC の共有バージョンでは、MFC 拡張 Dll と標準の MFC Dll をサポートします。  
  
-   共有 MFC ライブラリを使用するアプリケーションを構築することは、MFC 自体をリンクする必要はないために、静的にリンクされた MFC アプリケーションを構築するよりも高速です。 これは特に顕著に**デバッグ**ビルド リンカーがデバッグ情報を圧縮する必要があります: デバッグ情報が格納されている DLL とリンクするは、アプリケーション内でコンパクトにデバッグ情報が少なくします。  
  
 使用する理由いない MFC の共有バージョン。  
  
-   MFCxx.DLL (など) を配布することが必要です配布共有ライブラリを使用するアプリケーションをお客様のプログラムと共にライブラリです。 MFCxx.DLL は、多くの Dll のように自由に再頒布可能パッケージが、インストールする必要もあります DLL、セットアップ プログラムでします。 さらに、プログラムと MFC Dll 自体の両方に使用される C ランタイム ライブラリが含まれていると、MSVCRTxx.DLL を出荷する必要があります。  
  
##  <a name="_mfcnotes_how_to_write_an_mfc_extension_dll"></a> MFC 拡張 DLL を作成する方法  
 MFC 拡張 DLL は、クラスと MFC クラスの機能を装飾するために記述された関数を含む DLL です。 MFC 拡張 DLL は、アプリケーションを使用して、いくつか追加の考慮事項と同じ方法で共有 MFC Dll を使用します。  
  
-   ビルド プロセスは、いくつかの追加のコンパイラとリンカーのオプションを共有ライブラリを使用しているアプリケーションのビルドに似ています。  
  
-   MFC 拡張 DLL がない、 `CWinApp`-クラスを派生します。  
  
-   MFC 拡張 DLL は、特殊なを指定する必要があります`DllMain`です。 AppWizard 提供、`DllMain`関数を変更できます。  
  
-   MFC 拡張 DLL を得るために、初期化ルーチンを作成する、 **CDynLinkLibrary** MFC 拡張 DLL がエクスポートする場合`CRuntimeClass`es またはアプリケーションにリソース。 派生クラス**CDynLinkLibrary** MFC 拡張 DLL では、アプリケーションごとのデータを保持する必要がある場合に使用する可能性があります。  
  
 これらの考慮事項についてで詳しく説明します。 MFC Advanced Concepts サンプルを参照する必要がありますも[DLLHUSK](../visual-cpp-samples.md)が示されているため。  
  
-   共有ライブラリを使用してアプリケーションを構築します。 (DLLHUSK です。EXE はも他の Dll を MFC ライブラリに動的にリンクする MFC アプリケーションです。)  
  
-   MFC 拡張 DLL をビルドします。 (などの特殊フラグを注意してください`_AFXEXT`MFC 拡張 DLL のビルドで使用されている)  
  
-   MFC 拡張 Dll の 2 つの例です。 1 つは、限られたエクスポート (TESTDLL1) を含む MFC 拡張 DLL と全体のクラス インターフェイス (TESTDLL2) をエクスポートするその他の表示の基本的な構造を示しています。  
  
 クライアント アプリケーションとすべての MFC 拡張 Dll の両方には、MFCxx.DLL の同じバージョンを使用する必要があります。 MFC DLL の規則に準拠し、デバッグを提供する必要があります、小売 (/release) MFC 拡張 DLL のバージョン。 これにより、クライアント プログラムは、アプリケーションのデバッグとリテール版の両方のバージョンをビルドし、それらを適切なデバッグまたは製品版のすべての Dll にリンクできます。  
  
> [!NOTE]
>  C++ では、名前変更と、問題をエクスポート、ため MFC 拡張 DLL のエクスポート リストではさまざまなプラットフォームの Dll と同じ DLL のデバッグとリテール版バージョン間で異なる場合があります。 小売 MFCxx.DLL が約 2000 エクスポート エントリ ポイントです。デバッグ MFCxxD.DLL が約 3000 エクスポート エントリ ポイントです。  
  
### <a name="quick-note-on-memory-management"></a>メモリ管理ですばやくメモ  
 このテクニカル ノートの末尾付近の「メモリ管理」というタイトルのセクションでは、MFC の共有バージョンを使って MFCxx.DLL の実装について説明します。 情報は、単に DLL がここで説明されている MFC 拡張を実装するために知っておく必要があります。  
  
 場合と同様、同じアプリケーション内、MFCxx.DLL およびクライアント アプリケーションのアドレス空間に読み込まれるすべての MFC 拡張 Dll が、同じメモリ アロケーター、リソースを読み込み、MFC の「グローバル」状態には使用します。 正反対を行い、非 MFC DLL ライブラリと MFC と静的にリンクしている標準の MFC Dll がある各 DLL 独自のメモリ プールから割り当てられるために、このことは重要です。  
  
 MFC 拡張 DLL は、メモリを割り当て、その他のアプリケーションに割り当てられたオブジェクトにそのメモリできます混在自由にします。 また、共有ライブラリを使用するアプリケーションがクラッシュした場合、オペレーティング システムの保護は、DLL を共有している他の MFC アプリケーションの整合性を維持します。  
  
 同様に他の"global"、MFC の状態、リソースの読み込み元である現在の実行可能ファイルと同様に、クライアント アプリケーションと MFC 拡張 Dll だけでなくすべて MFCxx.DLL 自体の間で共有されます。  
  
### <a name="building-an-mfc-extension-dll"></a>MFC 拡張 DLL のビルド  
 AppWizard を使用するには、MFC 拡張 DLL プロジェクトを作成して、適切なコンパイラとリンカーの設定が自動的に生成します。 また、生成された、`DllMain`関数を変更できます。  
  
 MFC 拡張 DLL に既存のプロジェクトを変換する場合、標準的な規則を MFC の共有バージョンを使用してアプリケーションを構築するために開始し、次の操作を行います。  
  
-   追加 **/D_AFXEXT**コンパイラ フラグをします。 [プロジェクトのプロパティ] ダイアログで C/C++ ノードを選択します。 プリプロセッサのカテゴリを選択します。 追加`_AFXEXT`マクロの定義のフィールドには、セミコロンでの各アイテムを分離します。  
  
-   削除、 **/Gy**コンパイラ スイッチ。 [プロジェクトのプロパティ] ダイアログで C/C++ ノードを選択します。 コード生成のカテゴリを選択します。 「関数レベルのリンクの有効にする」オプションが有効でないことを確認します。 これは容易にできるように、リンカーは参照されていない関数を削除しないために、クラスをエクスポートします。 MFC DLL が MFC では、変更に静的にリンク元のプロジェクトが、通常のビルドに使用する場合、 **/MT [d]** コンパイラ オプションを **/MD [d]** です。  
  
-   使用して、エクスポート ライブラリをビルド、 **/DLL**リンクするにはオプションです。 これは、新しいターゲットを作成すると、対象の型として Win32 ダイナミック リンク ライブラリを指定するときに設定されます。  
  
### <a name="changing-your-header-files"></a>ヘッダー ファイルの変更  
 MFC 拡張 DLL の目的は、その機能を使用できる 1 つまたは複数のアプリケーションをいくつかの一般的な機能をエクスポートすることです。 これは、結局クラスと、クライアント アプリケーションで使用できるグローバル関数をエクスポートします。  
  
 行うには、各メンバー関数にマークされているようにインポートまたはエクスポートする適切なを確認する必要があります。 これには、特別な宣言が必要です:**方式**と **_declspec (dllimport)** です。 クライアント アプリケーションによって、クラスを使用している場合にたいとして宣言する **_declspec (dllimport)** です。 MFC 拡張 DLL 自体が構築されるときに、として宣言する必要がある**方式**です。 さらに、関数は、必要があります実際にはエクスポート、クライアント プログラムが読み込み時にバインドするようにします。  
  
 使用して、クラス全体をエクスポートする**AFX_EXT_CLASS**クラス定義にします。 このマクロとしてフレームワークによって定義**方式**とき **_AFXDLL**と`_AFXEXT`は定義されている、として定義されている **_declspec (dllimport)** とき`_AFXEXT`が定義されていません。 `_AFXEXT` MFC 拡張 DLL をビルドする場合は、前述のようは定義だけです。 例えば:  
  
```  
class AFX_EXT_CLASS CExampleExport : public CObject  
{ ... class definition ... };  
```  
  
### <a name="not-exporting-the-entire-class"></a>クラス全体をエクスポートしません。  
 クラスの個々 のために必要なメンバーのみをエクスポートする場合があります。 例では、エクスポートする場合の`CDialog`-派生したクラス、コンス トラクターのエクスポートのみが必要と`DoModal`を呼び出します。 DLL を使用してこれらのメンバーをエクスポートすることができます。DEF ファイルを使うことも**AFX_EXT_CLASS**をエクスポートする必要があります。 個々 のメンバーにほぼ同じ方法でします。  
  
 例えば:  
  
```  
class CExampleDialog : public CDialog  
{  
public:  
    AFX_EXT_CLASS CExampleDialog();
AFX_EXT_CLASS int DoModal();
*// rest of class definition  
 .  
 .  
 .  
};  
```  
  
 これを行うときに、不要になったクラスのすべてのメンバーをエクスポートするため、その他の問題に遭遇する可能性があります。 この問題は、MFC マクロの動作方法です。 MFC のヘルパー マクロのいくつか実際には、宣言または、データ メンバーを定義します。 したがって、これらのデータ メンバーは、DLL からエクスポートする必要があります。  
  
 たとえば、`DECLARE_DYNAMIC`マクロが定義されている次のように MFC 拡張 DLL をビルドする場合。  
  
```  
#define DECLARE_DYNAMIC(class_name) \  
protected: \  
    static CRuntimeClass* PASCAL _GetBaseClass();

\  
    public: \  
    static AFX_DATA CRuntimeClass class##class_name; \  
    virtual CRuntimeClass* GetRuntimeClass() const;

\  
```  
  
 開始する行"静的`AFX_DATA`"、クラスの内部で静的オブジェクトを宣言します。 このクラスを正しくエクスポートし、クライアントからのランタイム情報にアクセスします。EXE、この静的オブジェクトをエクスポートする必要があります。 修飾子を使って、静的オブジェクトが宣言されているため`AFX_DATA`、のみを定義する必要があります`AFX_DATA`する**方式**、DLL のビルド時として定義および **_declspec(dllimport)** 、クライアントの実行可能ファイルを作成するときにします。  
  
 前述したように、 **AFX_EXT_CLASS**はこの方法で既に定義されています。 だけを再定義する必要があります`AFX_DATA`と同じである**AFX_EXT_CLASS**クラス定義をします。  
  
 例えば:  
  
```  
#undef  AFX_DATA  
#define AFX_DATA AFX_EXT_CLASS  
class CExampleView : public CView  
{  
    DECLARE_DYNAMIC() *// ... class definition ...  
};  
#undef  AFX_DATA  
#define AFX_DATA  
```  
  
 常に MFC を使用、`AFX_DATA`のため、この手法は、このようなシナリオの使用は、マクロ内で定義するデータ項目上のシンボルです。 たとえばはの機能は`DECLARE_MESSAGE_MAP`します。  
  
> [!NOTE]
>  選択したクラスのメンバーではなく、クラス全体をエクスポートする場合は、静的データ メンバーが自動的にエクスポートします。  
  
 自動的にエクスポートすると同じ手法を使用することができます、`CArchive`抽出演算子のクラスを使用する、`DECLARE_SERIAL`と`IMPLEMENT_SERIAL`マクロです。 クラスの宣言を囲むことにより、アーカイブ演算子をエクスポート (内にある、します。H ファイル) を次のコード。  
  
```  
#undef AFX_API  
#define AFX_API AFX_EXT_CLASS  
 
<your class declarations here>  
 
#undef AFX_API  
#define AFX_API  
```  
  
### <a name="limitations-of-afxext"></a>_AFXEXT の制限事項  
 _ を使用する**AFXEXT** MFC 拡張 Dll が MFC 拡張 Dll の複数のレイヤーがあるない限りのプリプロセッサ シンボル。 MFC 拡張 Dll を呼び出す、または独自の MFC 拡張 Dll で、MFC クラスから派生し、内のクラスから派生するをした場合は、あいまいさを回避するプリプロセッサ シンボルを使用する必要があります。  
  
 問題は、その Win32、として任意のデータを明示的に宣言する必要があります**方式**、DLL からエクスポートする場合と **_declspec (dllimport)** DLL からインポートする場合は、します。 定義するときに`_AFXEXT`、MFC ヘッダーことを確認して**AFX_EXT_CLASS**が正しく定義されています。  
  
 場合などがある複数のレイヤー、1 つの記号**AFX_EXT_CLASS** MFC 拡張 DLL 可能性がある新しいクラスをエクスポートするだけでなく他の MFC 拡張 DLL からの他のクラスをインポートするために十分ではありません。 この問題を扱うために、DLL を使用すると、DLL 自体を構築することを示す特別なプリプロセッサ シンボルを使用します。 たとえば、次の 2 つの MFC 拡張 Dll、A.DLL、および B.DLL 想像してください。 それらの各ファイルはエクスポート A.H および B.H、一部のクラスです。 B.DLL は、A.DLL からクラスを使用します。 ヘッダー ファイルは、次のようになります。  
  
```  
/* A.H */  
#ifdef A_IMPL  
 #define CLASS_DECL_A   __declspec(dllexport)  
#else  
 #define CLASS_DECL_A   __declspec(dllimport)  
#endif  
 
class CLASS_DECL_A CExampleA : public CObject  
{ ... class definition ... };  
 
/* B.H */  
#ifdef B_IMPL  
 #define CLASS_DECL_B   __declspec(dllexport)  
#else  
 #define CLASS_DECL_B   __declspec(dllimport)  
#endif  
 
class CLASS_DECL_B CExampleB : public CExampleA  
{ ... class definition .. };  
```  
  
 A.DLL のビルド時にでビルド **/D A_IMPL** B.DLL のビルド時にでビルドおよび **/D B_IMPL**です。 個別のシンボルを使用すると DLL ごとに、CExampleB がエクスポートされ、B.DLL を構築するときに CExampleA をインポートします。 CExampleA が A.DLL を構築するときにエクスポートし、B.DLL (または他のクライアント) を使用する場合をインポートします。  
  
 組み込みを使用する場合、この種類の重ね順を実行できません**AFX_EXT_CLASS**と`_AFXEXT`プリプロセッサ シンボル。 上記の手法では、MFC 自体のメカニズムを使用して、OLE、データベース、およびネットワークの MFC 拡張 Dll をビルドする場合とほとんどの方法でこの問題は解決します。  
  
### <a name="not-exporting-the-entire-class"></a>クラス全体をエクスポートしません。  
 ここでも、クラス全体にエクスポートするときに、特別な注意する必要があります。 MFC マクロで作成されたために必要なデータ項目が正しくエクスポートされることを確認する必要があります。 再定義することによってこれ行う**AFX_DATA**特定のクラスのマクロにします。 これはクラス全体をエクスポートしない場合はいつでも行う必要があります。  
  
 例えば:  
  
```  
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
*//class definition   
 .  
 .  
 .  
};  
 
#undef AFX_DATA  
#define AFX_DATA  
```  
  
### <a name="dllmain"></a>DllMain  
 MFC 拡張 DLL のため、メインのソース ファイルに配置する必要がありますの正確なコードを次に示します。 標準のインクルード後を含んでいる必要があります。 AppWizard を使用して MFC 拡張 DLL 用のスターター ファイルを作成するときに提供されるに注意してください、`DllMain`します。  
  
```  
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
  
 呼び出し`AfxInitExtensionModule`モジュールのランタイム クラスをキャプチャ (`CRuntimeClass`構造体) のオブジェクト ファクトリだけでなく (`COleObjectFactory`オブジェクト) 使用するときに後で、 **CDynLinkLibrary**オブジェクトを作成します。 (省略可能) 呼び出し`AfxTermExtensionModule`により MFC クリーンアップするには、MFC 拡張 DLL の各プロセスのデタッチするときに (動作は、プロセスが終了したとき、またはの結果として、DLL がアンロードされたときに、 **FreeLibrary**呼び出す) MFC 拡張 DLL から. ほとんどの MFC 拡張 Dll が動的に読み込まれていないため (通常は、リンクされている、インポート ライブラリを使用して) への呼び出し`AfxTermExtensionModule`通常必要はありません。  
  
 場合は、アプリケーションを読み込んでし、MFC 拡張 Dll を動的に解放を必ず呼び出して`AfxTermExtensionModule`上記のようにします。 必ず使用して`AfxLoadLibrary`と`AfxFreeLibrary`(Win32 関数ではなく**LoadLibrary**と**FreeLibrary**)、アプリケーションは、複数のスレッドを使用している場合、または MFC を動的に読み込む場合拡張 DLL です。 使用して`AfxLoadLibrary`と`AfxFreeLibrary`MFC 拡張 DLL が読み込まれ、アンロードされるときに実行されるスタートアップおよびシャット ダウン コードに MFC のグローバル状態が破損していないことを保証します。  
  
 AFXDLLX のヘッダー ファイル。H には定義などの MFC 拡張 Dll で使用される構造の特別な定義が含まれています`AFX_EXTENSION_MODULE`と**CDynLinkLibrary**です。  
  
 グローバル*extensionDLL*のように宣言する必要があります。 MFC の 16 ビット バージョンとは異なりメモリを割り当てるし、MFCxx.DLL は時間によって完全に初期化されるため、この期間中に MFC 関数を呼び出す、`DllMain`と呼びます。  
  
### <a name="sharing-resources-and-classes"></a>リソースやクラスの共有  
 単純な MFC 拡張 Dll は、クライアント アプリケーションと、何も詳細に低帯域幅のいくつかの関数をエクスポートする必要があるだけです。 複数のユーザー インターフェイスの処理を要する Dll は、クライアント アプリケーションにリソースと C++ のクラスをエクスポートすることがあります。  
  
 リソースのエクスポートには、リソース リストを使います。 各アプリケーションでのシングル リンク リストは、 **CDynLinkLibrary**オブジェクト。 リソースを探すときにリソースを読み込む標準の MFC 実装の大部分まず現在のリソース モジュール (`AfxGetResourceHandle`) ウォークが見つからない場合の一覧**CDynLinkLibrary**オブジェクトを読み込もうとして、要求されたリソース。  
  
 C++ のクラス名を指定して、C++ オブジェクトの動的作成に似ています。 すべての MFC オブジェクトの逆シリアル化機構が必要な`CRuntimeClass`オブジェクトを登録できるように、以前に格納されたに基づいて必要な型の C++ オブジェクトを動的に作成して、再構築できます。  
  
 場合は、クライアント アプリケーションは、MFC 拡張 DLL 内のクラスを使用して`DECLARE_SERIAL`クラスをエクスポートして、クライアント アプリケーションに表示する必要があります。 ウォークすることによってこれはまた、 **CDynLinkLibrary**  ボックスの一覧です。  
  
 MFC Advanced Concepts サンプルの場合[DLLHUSK](../visual-cpp-samples.md)リストはようになります。  
  
```  
head ->   DLLHUSK.EXE   - or -   DLLHUSK.EXE  
 |      |  
    TESTDLL2.DLL TESTDLL2.DLL  
 |      |  
    TESTDLL1.DLL TESTDLL1.DLL  
 |      |  
 |      |  
    MFC90D.DLL MFC90.DLL  
```  
  
 MFCxx.DLL は通常、リソースやクラス リストの最後です。 MFCxx.DLL には、すべての標準コマンド Id のプロンプト文字列を含む、標準 MFC リソースのすべてが含まれます。 リストの末尾に置くことにより、Dll とクライアント アプリケーション自体にありませんが、独自に依存する、MFCxx.DLL 内の共有リソースには、標準 MFC リソースのコピー。  
  
 欠点はどのような Id に注意する必要のある、または名前を選択するを持つクライアント アプリケーションの名前空間に、リソースとすべての Dll のクラス名を結合します。 もちろんを無効にするこの機能するかをエクスポートしないリソースまたは**CDynLinkLibrary**をクライアント アプリケーションのオブジェクト。 [DLLHUSK](../visual-cpp-samples.md)サンプルでは、複数のヘッダー ファイルを使用して、共有リソースの名前空間を管理します。 参照してください[テクニカル ノート 35](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)共有リソース ファイルの使用に関するヒントを表示します。  
  
### <a name="initializing-the-dll"></a>DLL の初期化  
 前述のようは通常を作成する、 **CDynLinkLibrary**をクライアント アプリケーションのリソースやクラスをエクスポートするためにオブジェクト。 DLL を初期化するためにエクスポートされたエントリ ポイントを提供する必要があります。 最低でも、これは、引数を使用しないと、何も返さないを void ルーチンですが、どのようなことができます。  
  
 DLL を使用する各クライアント アプリケーションは、このアプローチを使用する場合、この初期化ルーチンを呼び出す必要があります。 これを割り当てることがあります**CDynLinkLibrary**内のオブジェクト、`DllMain`呼び出した後だけ`AfxInitExtensionModule`です。  
  
 初期化ルーチンを作成する必要があります、 **CDynLinkLibrary** MFC 拡張 DLL 情報までワイヤード (有線) の現在のアプリケーションのヒープ内のオブジェクト。 これは、次のように実行できます。  
  
```  
extern "C" extern void WINAPI InitXxxDLL()  
{  
    new CDynLinkLibrary(extensionDLL);

}  
```  
  
 ルーチンの名前、 *InitXxxDLL*この例では何でもかまいませんか。 ある必要はありません`extern "C"`、ただしはにより保守が簡単に、エクスポートの一覧を目的とします。  
  
> [!NOTE]
>  標準 MFC DLL からの MFC 拡張 DLL を使用する場合は、この初期化関数をエクスポートする必要があります。 この関数は、すべての MFC 拡張 DLL のクラスやリソースを使用する前に、標準 MFC DLL から呼び出される必要があります。  
  
### <a name="exporting-entries"></a>エントリのエクスポート  
 クラスをエクスポートして簡単な方法は、使用する **_declspec**と**方式**各クラスおよびグローバル関数をエクスポートします。 これにより、はるかに簡単になりますが、どのような関数がエクスポートされる経由で制御が少ないがあり、関数を序数でエクスポートすることはできませんので (後述) の各エントリ ポイントの名前を付けるより効率が下がります。 TESTDLL1 と TESTDLL2 は、そのエントリをエクスポートするのにこのメソッドを使用します。  
  
 内の各エントリの名前を付けて各エントリを手動でエクスポートするより効率的なメソッド (および MFCxx.DLL で使用されるメソッド) は、します。DEF ファイルです。 おエクスポート dll の (つまり、いないすべてのプロパティ)、のでおエクスポートたい特定のインターフェイスを決定します。 内のエントリの形式でリンカーに完全修飾名を指定する必要がありますのでが困難になります、します。DEF ファイルです。 これに対して、シンボリック リンクを本当に必要でない限り、C++ のクラスをエクスポートしないでください。  
  
 試した場合のクラスと C++ をエクスポートします。DEF ファイルをこの一覧を自動的に生成するツールを開発する場合があります。 これを行う 2 段階のリンクの処理を使用します。 エクスポートなしで、DLL をリンクし、生成するようにリンカーをします。マップ ファイルです。 します。マップ ファイルを使用するが、いくつかの並べ替えでのエクスポート エントリを生成する使用できるように、エクスポートするように関数の一覧を生成しています。DEF ファイルです。 MFCxx.DLL および OLE と数、千、データベースの MFC 拡張 Dll のエクスポートの一覧は、(ただし、完全に自動ではないと、while でごとに 1 回のチューニングによってする必要があります)、このようなプロセスを使用して生成されました。  
  
### <a name="cwinapp-vs-cdynlinklibrary"></a>CWinApp vs です。CDynLinkLibrary  
 MFC 拡張 DLL はありません、`CWinApp`の代わりに、作業する必要は、独自のオブジェクトを派生、 `CWinApp`-クライアント アプリケーションのオブジェクトを派生します。 つまり、クライアント アプリケーションがなど、メイン メッセージ ポンプ、アイドル ループを所有します。  
  
 新しいクラスを派生させることができる場合は、MFC 拡張 DLL は、各アプリケーション用の追加データを維持する必要があります、 **CDynLinkLibrary**上ルーチンを記述 InitXxxDLL で作成します。 実行すると、DLL がの現在のアプリケーションの一覧を確認できます**CDynLinkLibrary**特定の MFC 拡張 DLL 用の 1 つを検索するオブジェクト。  
  
### <a name="using-resources-in-your-dll-implementation"></a>DLL の実装でリソースの使用  
 前述のように、既定のリソースの負荷を進めていきますの一覧**CDynLinkLibrary**オブジェクトの最初の exe ファイルまたは要求されたリソースがある DLL を検索します。 すべての MFC Api だけでなく、内部のコードを使用してすべて`AfxFindResourceHandle`常駐が先に関係なく、任意のリソースを検索するリソースの一覧のすべての要素。  
  
 のみの特定の場所からリソースを読み込む場合は、Api を使用して`AfxGetResourceHandle`と`AfxSetResourceHandle`を古いハンドルを保存し、新しいハンドルを設定します。 クライアント アプリケーションに戻る前に、元のリソース ハンドルを必ず復元してください。 サンプル TESTDLL2 は、メニューを明示的に読み込むため、このアプローチを使用します。  
  
 リストを検索する場合、多少速度が低下することとリソース ID 範囲の管理が必要なことが欠点です。 いくつかの MFC 拡張 Dll にリンクするクライアント アプリケーションが DLL のインスタンス ハンドルを指定せずに、DLL が提供するリソースを使用することの利点があります。 `AfxFindResourceHandle` は、リソース リストを検索して一致するリソースを見つけるのに使われる API です。 リソースの名前と型を受け取り、最初に一致したリソース ハンドル (または NULL) を返します。  
  
##  <a name="_mfcnotes_writing_an_application_that_uses_the_dll_version"></a> DLL のバージョンを使用するアプリケーションの作成  
  
### <a name="application-requirements"></a>アプリケーションの要件  
 MFC の共有バージョンを使用するアプリケーションは、いくつかの単純な規則に従う必要があります。  
  
-   必要があります、`CWinApp`オブジェクトおよびメッセージ ポンプの標準的な規則に従います。  
  
-   これは、一連の必要なコンパイラ フラグ (下記参照) でコンパイルする必要があります。  
  
-   MFCxx インポート ライブラリとリンクする必要があります。 必要なコンパイラ フラグを設定するでは、MFC ヘッダーは、アプリケーションとリンクする必要があるためのライブラリをリンク時に決定されます。  
  
-   実行可能ファイルを実行するには、MFCxx.DLL は、または Windows システム ディレクトリのパスにする必要があります。  
  
### <a name="building-with-the-development-environment"></a>開発環境でビルドします。  
 内部のメイクファイルのほとんどの標準の既定値を使用している場合は、DLL のバージョンをビルドするプロジェクトを簡単に変更できます。  
  
 次の手順では、一部を示しますにリンクされている、正しく機能している MFC アプリケーションがあると仮定します。(デバッグ) 用の LIB と NAFXCW です。LIB (製品) を使用し、MFC ライブラリの共有バージョンを使用するように変換します。 Visual C 環境を実行して、内部プロジェクト ファイルが存在します。  
  
1.  **プロジェクト** メニューのをクリックして**プロパティ**です。 **全般**ページで、**プロジェクトの既定値**、Microsoft Foundation Classes 'éý'**共有 DLL で MFC を使用する**(MFCxx(d).dll) です。  
  
### <a name="building-with-nmake"></a>NMAKE を使用した構築  
 コンパイラとリンカーのオプションをサポートするために、メイクファイルを編集する必要が、Visual C の外部メイクファイルの機能を使用しているか (nmake の) が直接使用している場合  
  
 コンパイラ フラグが必要です。  
  
 **/方法/MD**  
 **/方法**  
  
 MFC の標準ヘッダーには、このシンボルを定義する必要があります。  
  
 **/MD**  
 アプリケーションは、C ランタイム ライブラリの DLL バージョンを使用する必要があります。  
  
 その他のすべてのコンパイラ フラグでは、MFC の既定値 (たとえば、デバッグ時の _DEBUG) に従います。  
  
 リンカーのライブラリ リストを編集します。 変更の一部を示します。LIB MFCxxD.LIB をし NAFXCW を変更します。Lib MFCxx.LIB を設定します。 LIBC を置き換えます。LIB MSVCRT とします。LIB。 その他の MFC ライブラリでは MFCxxD.LIB が配置されている重要な**する前に**C ランタイム ライブラリです。  
  
 必要に応じて追加**用**小売とデバッグの両方のリソース コンパイラのオプションを (1 つでのリソースをコンパイルする **/R**)。 これにより、MFC Dll に存在するリソースを共有することによって、最終的な実行可能ファイルを小さなにします。  
  
 これらの変更が行われた後に、完全な再構築を使用することが必要です。  
  
### <a name="building-the-samples"></a>サンプルのビルド  
 MFC のサンプル プログラムのほとんどは、Visual C とは、コマンドラインからの共有 (nmake の) と互換性のあるメイクファイルから構築できます。  
  
 MFCxx.DLL を使用して、上記のサンプルのいずれかに変換することができますにロードします。MAK は、ファイルを Visual C にし、前述のようにプロジェクトのオプションを設定します。 指定できます (nmake の) ビルドを使用するかどうか、"AFXDLL = 1"、NMAKE でとコマンド ラインは、サンプルをビルド共有 MFC ライブラリを使用します。  
  
 MFC Advanced Concepts サンプル[DLLHUSK](../visual-cpp-samples.md)は MFC の DLL バージョンでビルドします。 このサンプルはだけでなく、MFCxx.DLL にリンクされているアプリケーションを構築する方法を示していますが、また、MFC DLL パッケージング オプション MFC 拡張 Dll がこのテクニカル ノートの後半で説明されているなどの他の機能を示しています。  
  
### <a name="packaging-notes"></a>パッケージの注意事項  
 製品版の Dll (MFCxx [U] です。DLL) は自由に再頒布可能パッケージ。 Dll のデバッグ バージョンは、自由に再頒布可能パッケージできない、アプリケーションの開発時にのみ使用する必要があります。  
  
 デバッグ バージョンの Dll のデバッグ情報が提供されます。 Visual C デバッガーを使用すると、DLL と同様に、アプリケーションの実行をトレースできます。 リリースの Dll (MFCxx [U] です。DLL) デバッグ情報は含まれません。  
  
 カスタマイズまたは、Dll を再構築する場合を呼び出す必要がありますに何か"MFCxx"、MFC SRC ファイル ビルド以外。MAK は、ビルド オプションについて説明し、DLL の名前を変更するためのロジックが含まれています。 これらの Dll は多くの MFC アプリケーションで共有される可能性があるために、ファイル名の変更は必要に応じて、です。 MFC Dll 置換後の文字列のカスタマイズ バージョンを持つ共有 MFC Dll を使用して別の MFC アプリケーションを中断、システムにインストールされている可能性があります。  
  
 MFC Dll を再構築することをお勧めします。  
  
##  <a name="_mfcnotes_how_the_mfc30.dll_is_implemented"></a> MFCxx.DLL を実装する方法  
 次のセクションでは、MFC の DLL (MFCxx.DLL および MFCxxD.DLL) を実装する方法について説明します。 理解することの詳細をここでもありませんすべてを実行する場合に重要ですがアプリケーションを使用して、MFC DLL を使用します。 ここで詳細が MFC 拡張 DLL を記述する方法を理解するために重要ではありませんが、この実装を理解するために役立つ、独自の DLL を作成します。  
  
### <a name="implementation-overview"></a>実装の概要  
 MFC DLL は MFC 拡張 DLL の特殊なケースでは実際に前述のとおりです。 クラスの数が多いのエクスポートの非常に大きな数があります。 その他いくつか MFC DLL を実行できるように、正規の MFC 拡張 DLL よりも特別です。  
  
### <a name="win32-does-most-of-the-work"></a>Win32 のほとんどの作業には  
 MFC の 16 ビット バージョンでは、いくつかの特別な手法がアプリごとのデータを含む履歴のセグメント 80x86 アセンブリ コード、プロセスあたりの例外コンテキスト、およびその他の手法によって作成された特別なセグメントが必要です。 Win32 直接プロセスごとのデータのサポート、DLL をほとんどの目的はします。 MFCxx.DLL は、ほとんどの場合 NAFXCW だけです。LIB の DLL にパッケージ化します。 MFC ソース コードを見ると場合、必要になるほとんどの特殊なケースがあるため、ほとんどの #ifdef _AFXDLL がありません。 具体的には Windows 3.1 (それ以外の場合は Win32s と呼ばれます) の Win32 扱うである特殊なケースです。 Win32s は、MFC DLL がスレッド ローカル ストレージ (TLS) をローカル データの処理を取得する Win32 Api を使用する必要がありますので直接サポート プロセスごとの DLL データは表示されません。  
  
### <a name="impact-on-library-sources-additional-files"></a>ライブラリのソース、追加のファイルへの影響  
 影響、 **_AFXDLL**標準の MFC クラス ライブラリのソースとヘッダーのバージョンは比較的重要でないです。 ファイルがある特別なバージョン (AFXV_DLL です。H) だけでなく、追加のヘッダー ファイル (AFXDLL_ です。H) メイン AFXWIN で含まれます。H ヘッダー。 AFXDLL_ です。H ヘッダーが含まれています、 **CDynLinkLibrary**クラスおよびその他の実装の詳細を両方の **_AFXDLL**アプリケーションや MFC 拡張 Dll です。 AFXDLLX です。H ヘッダーは、MFC 拡張 Dll (詳細については上記参照) を構築するために提供されます。  
  
 MFC ライブラリは、MFC SRC を正規のソース下にある追加の条件付きコードがある、 **_AFXDLL** #ifdef です。 追加のソース ファイル (DLLINIT です。CPP) には、余分な DLL の初期化コードなどの MFC の共有バージョンが含まれています。  
  
 MFC の共有バージョンをビルドするために、追加のファイルが提供されます。 (下記を参照、DLL をビルドする方法の詳細です。)  
  
-   次の 2 つです。DEF ファイルは、デバッグ (MFCxxD.DEF) のエントリ ポイントを MFC DLL のエクスポートに使用し、リリース (MFCxx.DEF) バージョンの DLL のです。  
  
-   .RC ファイル (ビルドします。RC) には、dll のすべての標準 MFC リソースと VERSIONINFO リソースが含まれています。  
  
-   です。CLW ファイル (ビルドします。MFC の参照は許可するクラスの使用の ClassWizard CLW) が提供されます。 注: この機能は、MFC の DLL バージョンを特定できません。  
  
### <a name="memory-management"></a>メモリ管理  
 MFCxx.DLL を使用するアプリケーションでは、MSVCRTxx.DLL、共有の C ランタイム DLL によって提供される一般的なメモリ アロケーターを使用します。 アプリケーション、任意の MFC 拡張 Dll と MFC Dll 自体は、この共有メモリ アロケーターを使用します。 共有 DLL を使用するとメモリの割り当てに、MFC Dll は、アプリケーションまたはその逆に後で解放されるメモリを割り当てることができます。 アプリケーションと DLL の両方が同じアロケーターを使用する必要があります、ため、C++ のグローバルはオーバーライドできません`operator new`または`operator delete`です。 C ランタイムのメモリ割り当てルーチンの残りの部分に同じ規則が適用されます (など`malloc`、 `realloc`、**空き**、およびその他)。  
  
### <a name="ordinals-and-class-declspecdllexport-and-dll-naming"></a>序数クラス方式と DLL の名前を付ける  
 使用していません、 `class` **方式**C コンパイラの機能です。 代わりに、エクスポートの一覧は、クラス ライブラリのソース (MFCxx.DEF および MFCxxD.DEF) に含まれてです。 これらを選択のエントリ ポイント (関数とデータ) のセットのみがエクスポートされます。 MFC プライベートな実装の関数やクラスなど、その他の記号はエクスポートされていないすべてのエクスポートが常駐しているまたは非常駐名前テーブルでの文字列名を指定せずに序数で行われます。  
  
 使用して`class`**方式**可能性がありますが MFC では、既定のメカニズムをエクスポートするような大規模な DLL の場合、小さい Dll を作成するための実用的な代替は効率性とキャパシティ制限します。  
  
 このすべては、意味は、大量のリリースは、多くの実行を損なうことや、読み込み速度なし約 800 KB のみ MFCxx.DLL の機能をパッケージおことができます。 MFCxx.DLL が大きく 100 K この手法でなかったために使用します。 これもできるようになりますの最後に他のエントリ ポイントを追加します。序数でエクスポートする速度とサイズの効率性を損なうことがなく単純なバージョン管理を許可する DEF ファイルです。 MFC クラス ライブラリ内のメジャー バージョンの変更履歴は、ライブラリの名前に変更されます。 つまり、MFC30 です。DLL は、MFC クラス ライブラリのバージョン 3.0 を含む再頒布可能 DLL です。 この DLL のアップグレードと仮定の MFC 3.1 では、DLL の名前は MFC31 します。DLL 代わりにします。 もう一度、カスタムのバージョンの MFC DLL を生成するために MFC ソース コードを変更する場合は、別の名前 (および可能であれば"で MFC を使用"名前のない) を使用します。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

