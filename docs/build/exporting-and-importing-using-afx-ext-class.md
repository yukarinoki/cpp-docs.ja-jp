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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328607"
---
# <a name="exporting-and-importing-using-afx_ext_class"></a>AFX_EXT_CLASS を使ったエクスポート/インポート

[MFC 拡張 DLL](extension-dlls-overview.md) では、マクロ **AFX_EXT_CLASS** を使用してクラスがエクスポートされます。MFC 拡張 DLL にリンクする実行可能ファイルは、このマクロを使用してクラスをインポートします。 **AFX_EXT_CLASS** マクロでは、MFC 拡張 DLL のビルドに使用されるものと同じヘッダー ファイルを、DLL にリンクする実行可能ファイルと共に使用できます。

DLL のヘッダー ファイルで、次のようにクラスの宣言に **AFX_EXT_CLASS** キーワードを追加します。

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

このマクロは、プリプロセッサ シンボル `_AFXDLL` と `_AFXEXT` が定義されている場合に `__declspec(dllexport)` として MFC によって定義されます。 ただし、`_AFXDLL` が定義され `_AFXEXT` が定義されていない場合、マクロは `__declspec(dllimport)` として定義されます。 プリプロセッサ シンボル `_AFXDLL` が定義されている場合、MFC の共有バージョンがターゲット実行可能ファイル (DLL またはアプリケーション) によって使用されていることを示します。 `_AFXDLL` と `_AFXEXT` の両方が定義されている場合、ターゲットの実行可能ファイルが MFC 拡張 DLL であることを示します。

`AFX_EXT_CLASS` は、MFC 拡張 DLL からエクスポートするときに `__declspec(dllexport)` として定義されているため、.def ファイル内のすべてのクラスのシンボルに装飾名を配置することなく、クラス全体をエクスポートできます。

この方法を使用すると、クラスの .def ファイルとすべての装飾名を作成することは避けられますが、.def ファイルを作成すると、名前を序数でエクスポートできるためより効率的です。 .def ファイル方式のエクスポートを使用する場合は、以下のコードをヘッダー ファイルの先頭と末尾に記述します。

```cpp
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

> [!CAUTION]
> インライン関数をエクスポートする場合は、バージョンの競合が発生する可能性があるため、注意してください。 インライン関数はアプリケーション コードに展開されます。そのため、後で関数を書き直す場合、アプリケーション自体が再コンパイルされない限り、更新されません。 通常、DLL 関数は、それらを使用するアプリケーションをリビルドせずに更新できます。

## <a name="exporting-individual-members-in-a-class"></a>クラス内の個々のメンバーのエクスポート

場合によっては、クラスの個々のメンバーをエクスポートする必要があります。 たとえば、`CDialog` 派生クラスをエクスポートする場合に、コンストラクターと `DoModal` 呼び出しのエクスポートだけが必要な場合があります。 `AFX_EXT_CLASS` は、エクスポートする必要がある個々のメンバーに対して使用できます。

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

クラスのすべてのメンバーをエクスポートするわけではないため、MFC マクロの動作方法が理由で、追加の問題が発生する可能性があります。 MFC のヘルパー マクロのいくつかは、実際にデータ メンバーを宣言または定義します。 したがって、これらのデータ メンバーも DLL からエクスポートする必要があります。

たとえば、MFC 拡張 DLL をビルドするときに、`DECLARE_DYNAMIC` マクロは次のように定義されます。

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
   static CRuntimeClass* PASCAL _GetBaseClass(); \
public: \
   static AFX_DATA CRuntimeClass class##class_name; \
   virtual CRuntimeClass* GetRuntimeClass() const; \
```

static `AFX_DATA` で始まる行は、クラス内の静的オブジェクトを宣言しています。 このクラスを正しくエクスポートし、クライアント実行可能ファイルからランタイム情報にアクセスするには、この静的オブジェクトをエクスポートする必要があります。 静的オブジェクトは修飾子 `AFX_DATA` を使用して宣言されているため、DLL をビルドするときには `AFX_DATA` が `__declspec(dllexport)` になるように定義し、クライアント実行可能ファイルをビルドするときには `__declspec(dllimport)` として定義するだけで済みます。 `AFX_EXT_CLASS` は既にこの方法で定義されているため、`AFX_DATA` を再定義して、クラス定義の `AFX_EXT_CLASS` と同じにするだけです。

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

MFC では、マクロ内で定義されているデータ項目に対して常に `AFX_DATA` シンボルが使用されるため、この方法はすべてのシナリオで機能します。 たとえば、`DECLARE_MESSAGE_MAP` でも機能します。

> [!NOTE]
> クラスの選択したメンバーではなくクラス全体をエクスポートする場合は、静的データ メンバーは自動的にエクスポートされます。

### <a name="what-do-you-want-to-do"></a>実行する操作

- [.def ファイルを使用して DLL からエクスポートする](exporting-from-a-dll-using-def-files.md)

- [__declspec(dllexport) を使用して DLL からエクスポートする](exporting-from-a-dll-using-declspec-dllexport.md)

- [C 言語の実行可能ファイルで使用する C++ 関数をエクスポートする](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [C または C++ 言語の実行可能ファイルで使用する C 関数をエクスポートする](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [エクスポート方式の使い分け](determining-which-exporting-method-to-use.md)

- [__declspec(dllimport) を使用してアプリケーションにインポートする](importing-into-an-application-using-declspec-dllimport.md)

- [DLL の初期化](run-time-library-behavior.md#initializing-a-dll)

### <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [装飾名](reference/decorated-names.md)

- [インライン関数のインポートとエクスポート](importing-and-exporting-inline-functions.md)

- [相互インポート](mutual-imports.md)

## <a name="see-also"></a>関連項目

[DLL からのエクスポート](exporting-from-a-dll.md)
