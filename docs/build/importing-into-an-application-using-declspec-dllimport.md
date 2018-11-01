---
title: __declspec(dllimport) を使ったアプリケーションへのインポート
ms.date: 11/04/2016
f1_keywords:
- __declspec
- dllimport
helpviewer_keywords:
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
ms.openlocfilehash: 925cd588c1851c6fb135fffbb83e9cfd680bea28
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50610473"
---
# <a name="importing-into-an-application-using-declspecdllimport"></a>__declspec(dllimport) を使ったアプリケーションへのインポート

あるプログラムが DLL によって定義されたパブリック シンボルを使うことを、シンボルをインポートすると言います。 ヘッダー ファイルを作成するときの Dll を使用して、使用すると、ビルドするアプリケーションを使用して、 **_declspec**パブリック シンボルの宣言。 キーワード **_declspec**や .def ファイルをエクスポートするかどうかの動作、**方式**キーワード。

コードを読みやすくするためのマクロを定義 **_declspec**マクロを使用して各インポート シンボルを宣言するとします。

```
#define DllImport   __declspec( dllimport )

DllImport int  j;
DllImport void func();
```

使用して **_declspec**は関数の宣言で省略可能ですが、このキーワードを使用する場合、コンパイラがより効率的なコードを生成します。 ただし、使用する必要があります **_declspec**のインポートの実行可能ファイル、DLL のパブリック データ シンボルとオブジェクトにアクセスします。 DLL を使う場合は、引き続きインポート ライブラリとリンクする必要があることに注意してください。

DLL とクライアント アプリケーションには、同じヘッダー ファイルを使うことができます。 こうする場合は、DLL のビルドとクライアント アプリケーションのビルドの区別を示すために、専用のプリプロセッサ シンボルを使います。 例えば:

```
#ifdef _EXPORTING
   #define CLASS_DECLSPEC    __declspec(dllexport)
#else
   #define CLASS_DECLSPEC    __declspec(dllimport)
#endif

class CLASS_DECLSPEC CExampleA : public CObject
{ ... class definition ... };
```

## <a name="what-do-you-want-to-do"></a>実行する操作

- [DLL を初期化します。](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [インポートとエクスポートのインライン関数](../build/importing-and-exporting-inline-functions.md)

- [相互インポート](../build/mutual-imports.md)

## <a name="see-also"></a>関連項目

[アプリケーションへのインポート](../build/importing-into-an-application.md)