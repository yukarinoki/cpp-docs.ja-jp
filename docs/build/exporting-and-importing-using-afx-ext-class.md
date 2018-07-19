---
title: AFX_EXT_CLASS を使ったエクスポート/インポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- afx_ext_class
dev_langs:
- C++
helpviewer_keywords:
- AFX_EXT_CLASS macro
- exporting classes [C++]
- importing DLLs [C++]
- extension DLLs [C++], exporting classes
- executable files [C++], importing classes
- exporting DLLs [C++], AFX_EXT_CLASS macro
ms.assetid: 6b72cb2b-e92e-4ecd-bcab-c335e1d1cfde
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f6cc853c66afae72d6e426d800c0443ab206ab20
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371061"
---
# <a name="exporting-and-importing-using-afxextclass"></a>AFX_EXT_CLASS を使ったエクスポート/インポート  
  
[MFC 拡張 Dll](../build/extension-dlls-overview.md)マクロを使用して**AFX_EXT_CLASS**をエクスポートするクラスです。 MFC 拡張 DLL にリンクする実行可能ファイルでは、マクロを使用してクラスをインポートします。 **AFX_EXT_CLASS**マクロ、DLL は、DLL にリンクする実行可能ファイルで使用できる MFC の拡張機能の構築に使用される同じヘッダー ファイルです。  
  
 DLL のヘッダー ファイルを追加、 **AFX_EXT_CLASS**キーワードを次のように、クラスの宣言に。  
  
```cpp  
class AFX_EXT_CLASS CMyClass : public CDocument  
{  
// <body of class>  
};  
```  
  
としての MFC でこのマクロが定義されている`__declspec(dllexport)`ときプリプロセッサ シンボル`_AFXDLL`と`_AFXEXT`定義されます。 としてマクロが定義されているが、`__declspec(dllimport)`とき`_AFXDLL`が定義されていると`_AFXEXT`が定義されていません。 定義した場合、プリプロセッサ シンボル`_AFXDLL`ターゲット実行可能ファイル (DLL またはアプリケーション) によって、MFC の共有バージョンを使用していることを示します。 ときに両方`_AFXDLL`と`_AFXEXT`は実行可能ファイルの MFC 拡張 DLL は定義されている場合、これを示します。  
  
`AFX_EXT_CLASS`として定義されて`__declspec(dllexport)`MFC 拡張 DLL からエクスポートするときは、.def ファイル内のすべてにそのクラスのシンボルの装飾名をかけることがなくクラス全体をエクスポートできます。  
  
名前は序数でエクスポートされることができますので、このメソッドを使用して、.def ファイルとすべてのクラスの装飾名の作成は避けることができますがより効率的 .def ファイルを作成します。 メソッドを使用するには、.def ファイルをエクスポートするには、先頭とヘッダー ファイルの末尾に次のコードを配置します。  
  
```cpp  
#undef AFX_DATA  
#define AFX_DATA AFX_EXT_DATA  
// <body of your header file>  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
> [!CAUTION]
>  バージョン間の競合の可能性があるために、インライン関数をエクスポートするときに注意が必要します。 インライン関数は、アプリケーション コードに展開されます。したがって、関数を書き換えた後で場合、それが更新されない、アプリケーション自体を再コンパイルする場合を除き、します。 通常は、それらを使用するアプリケーションを再構築しないで DLL 関数を更新できます。  
  
## <a name="exporting-individual-members-in-a-class"></a>クラスの個別のメンバーをエクスポートします。  
  
場合によって、クラスの個々 のメンバーをエクスポートすることができます。 例では、エクスポートする場合の`CDialog`-派生したクラス、コンス トラクターのエクスポートのみが必要と`DoModal`を呼び出します。 使用することができます`AFX_EXT_CLASS`をエクスポートする必要があります。 個々 のメンバーにします。  
  
例えば:  
  
```cpp  
class CExampleDialog : public CDialog  
{  
public:  
   AFX_EXT_CLASS CExampleDialog();  
   AFX_EXT_CLASS int DoModal();  
   ...  
   // rest of class definition  
   ...  
};  
```  
  
クラスのすべてのメンバーをエクスポートしないために実行すると、その他の問題に方法により、MFC マクロの動作。 MFC のヘルパー マクロのいくつか実際には、宣言または、データ メンバーを定義します。 そのため、これらのデータ メンバーでありも、DLL からエクスポートする必要があります。  
  
たとえば、`DECLARE_DYNAMIC`マクロが定義されている次のように MFC 拡張 DLL をビルドする場合。  
  
```cpp  
#define DECLARE_DYNAMIC(class_name) \  
protected: \  
   static CRuntimeClass* PASCAL _GetBaseClass(); \  
public: \  
   static AFX_DATA CRuntimeClass class##class_name; \  
   virtual CRuntimeClass* GetRuntimeClass() const; \  
```  
  
静的で始まる行`AFX_DATA`クラスの内部で静的なオブジェクトが宣言されています。 このクラスを正しくエクスポートをクライアント実行可能ファイルの実行時情報にアクセスするには、この静的オブジェクトをエクスポートする必要があります。 修飾子を使って、静的オブジェクトが宣言されているため`AFX_DATA`、のみを定義する必要があります`AFX_DATA`する`__declspec(dllexport)`、DLL のビルド時として定義し、`__declspec(dllimport)`クライアントの実行可能ファイルを作成するときにします。 `AFX_EXT_CLASS`は既に定義されて、この方法でのみ再定義する必要`AFX_DATA`と同じである`AFX_EXT_CLASS`クラス定義をします。  
  
例えば:  
  
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
  
MFC が常に使用するため、`AFX_DATA`記号、マクロ内で定義するデータ項目をこのようなシナリオの場合は、この手法をアプローチを使用します。 たとえば、この機能に対して機能`DECLARE_MESSAGE_MAP`します。  
  
> [!NOTE]
>  選択したクラスのメンバーではなく、クラス全体をエクスポートする場合は、静的データ メンバーが自動的にエクスポートします。  
  
### <a name="what-do-you-want-to-do"></a>実行する操作  
  
-   [.Def ファイルを使った DLL からエクスポートします。](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [関数を使った DLL からエクスポートします。](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [C 言語の実行可能ファイルで使用するための C++ 関数をエクスポートします。](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [C または C++ 言語の実行可能ファイルで使用するための C 関数をエクスポートします。](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [エクスポート方式を使い分け](../build/determining-which-exporting-method-to-use.md)  
  
-   [_Declspec (dllimport) を使用してアプリケーションをインポートします。](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL を初期化します。](../build/run-time-library-behavior.md#initializing-a-dll)  
  
### <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
  
-   [装飾名](../build/reference/decorated-names.md)  
  
-   [インポートして、インライン関数をエクスポートします。](../build/importing-and-exporting-inline-functions.md)  
  
-   [相互インポート](../build/mutual-imports.md)  
  
## <a name="see-also"></a>関連項目  
 [DLL からのエクスポート](../build/exporting-from-a-dll.md)