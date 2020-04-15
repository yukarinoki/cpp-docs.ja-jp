---
title: AFX_EXT_CLASS を使ったエクスポート/インポート
ms.date: 11/04/2016
f1_keywords:
- afx_ext_class
helpviewer_keywords:
- AFX_EXT_CLASS macro
- exporting classes [C++]
- importing DLLs [C++]
- extension DLLs [C++], exporting classes
- executable files [C++], importing classes
- exporting DLLs [C++], AFX_EXT_CLASS macro
ms.assetid: 6b72cb2b-e92e-4ecd-bcab-c335e1d1cfde
ms.openlocfilehash: 95c72f8251a8a59833483eb948709c80a69d03d7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328607"
---
# <a name="exporting-and-importing-using-afx_ext_class"></a>AFX_EXT_CLASS を使ったエクスポート/インポート

[MFC 拡張 DLL は](extension-dlls-overview.md)、マクロ**AFX_EXT_CLASS**を使用してクラスをエクスポートします。MFC 拡張 DLL にリンクする実行可能ファイルは、マクロを使用してクラスをインポートします。 **AFX_EXT_CLASS**マクロでは、MFC 拡張 DLL のビルドに使用されるヘッダー ファイルと同じヘッダー ファイルを、DLL にリンクする実行可能ファイルと共に使用できます。

DLL のヘッダー ファイルで、次のようにクラスの宣言に**AFX_EXT_CLASS**キーワードを追加します。

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

このマクロは、プリプロセッサシンボル`__declspec(dllexport)``_AFXDLL`と`_AFXEXT`定義時に MFC によって定義されます。 しかし、マクロはいつ`__declspec(dllimport)``_AFXDLL`定義され、定義されていない`_AFXEXT`として定義されます。 プリプロセッサ シンボル`_AFXDLL`を定義すると、共有バージョンの MFC がターゲット実行可能ファイル (DLL またはアプリケーション) によって使用されていることを示します。 両方`_AFXDLL`を定義`_AFXEXT`すると、ターゲット実行可能ファイルが MFC 拡張 DLL であることを示します。

MFC`AFX_EXT_CLASS`拡張`__declspec(dllexport)`DLL からエクスポートする場合と定義されているため、.def ファイル内のクラスのすべてのシンボルに装飾された名前を付けずに、クラス全体をエクスポートできます。

このメソッドを使用して、.def ファイルとクラスのすべての装飾名を作成することは避けることができますが、名前を序数でエクスポートできるため、.def ファイルの作成の方が効率的です。 .def ファイルのエクスポート方法を使用するには、ヘッダー ファイルの先頭と末尾に次のコードを記述します。

```cpp
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

> [!CAUTION]
> インライン関数をエクスポートする場合は、バージョンの競合が発生する可能性があるため、注意が必要です。 インライン関数はアプリケーション コードに展開されます。したがって、後で関数を書き直しても、アプリケーション自体が再コンパイルされない限り、関数は更新されません。 通常、DLL 関数は、DLL 関数を使用するアプリケーションを再構築せずに更新できます。

## <a name="exporting-individual-members-in-a-class"></a>クラス内の個々のメンバーのエクスポート

クラスの個々のメンバをエクスポートする場合があります。 たとえば、派生クラスを`CDialog`エクスポートする場合は、コンストラクターと`DoModal`呼び出しのみをエクスポートする必要があります。 エクスポートする必要`AFX_EXT_CLASS`がある個々のメンバーで使用できます。

次に例を示します。

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

クラスのすべてのメンバーをエクスポートする必要がなくなったため、MFC マクロの動作方法により、追加の問題が発生する可能性があります。 MFC のヘルパー マクロのいくつかは、実際にはデータ メンバーを宣言または定義します。 したがって、これらのデータ メンバーも DLL からエクスポートする必要があります。

たとえば、MFC`DECLARE_DYNAMIC`拡張 DLL をビルドする場合、マクロは次のように定義されます。

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
   static CRuntimeClass* PASCAL _GetBaseClass(); \
public: \
   static AFX_DATA CRuntimeClass class##class_name; \
   virtual CRuntimeClass* GetRuntimeClass() const; \
```

static`AFX_DATA`で始まる行は、クラス内で静的オブジェクトを宣言しています。 このクラスを正しくエクスポートし、クライアント実行可能ファイルからランタイム情報にアクセスするには、この静的オブジェクトをエクスポートする必要があります。 静的オブジェクトは`AFX_DATA`修飾子 で宣言されるため、DLL をビルドするときに定義`AFX_DATA``__declspec(dllexport)`し、クライアント実行可能ファイルをビルドするときにそれを定義`__declspec(dllimport)`する必要があります。 既`AFX_EXT_CLASS`にこのように定義されているため、クラス定義の周囲と`AFX_DATA``AFX_EXT_CLASS`同じに再定義する必要があります。

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

MFC はマクロ内`AFX_DATA`で定義するデータ項目に常にシンボルを使用するため、この手法はこのようなすべてのシナリオに対して機能します。 たとえば、この機能は`DECLARE_MESSAGE_MAP`.

> [!NOTE]
> クラスの選択されたメンバーではなく、クラス全体をエクスポートする場合、静的データ メンバーは自動的にエクスポートされます。

### <a name="what-do-you-want-to-do"></a>目的に合ったトピックをクリックしてください

- [.def ファイルを使った DLL からのエクスポート](exporting-from-a-dll-using-def-files.md)

- [__declspec(dllexport) を使った DLL からのエクスポート](exporting-from-a-dll-using-declspec-dllexport.md)

- [C 言語の実行形式で使う C++ 関数のエクスポート](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C/C++ 言語の実行形式で使う C 関数のエクスポート](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [使用するエクスポート方法を決定する](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) を使用してアプリケーションにインポートする](importing-into-an-application-using-declspec-dllimport.md)

- [DLL の初期化](run-time-library-behavior.md#initializing-a-dll)

### <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [装飾名](reference/decorated-names.md)

- [インライン関数のインポートとエクスポート](importing-and-exporting-inline-functions.md)

- [相互輸入](mutual-imports.md)

## <a name="see-also"></a>関連項目

[DLL からのエクスポート](exporting-from-a-dll.md)
