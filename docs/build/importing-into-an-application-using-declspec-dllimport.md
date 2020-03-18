---
title: __declspec(dllimport) を使ったアプリケーションへのインポート
ms.date: 11/04/2016
helpviewer_keywords:
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
ms.openlocfilehash: fd7d42ec5a76b92aa789a3a20f38e6b2c0fd2cb1
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440416"
---
# <a name="import-into-an-application-using-__declspecdllimport"></a>__declspec(dllimport) を使ったアプリケーションへのインポート

あるプログラムが DLL によって定義されたパブリック シンボルを使うことを、シンボルをインポートすると言います。 Dll を使用してでビルドするアプリケーションのヘッダーファイルを作成する場合は、パブリックシンボルの宣言で **__declspec (dllimport)** を使用します。 キーワード **__declspec (dllimport)** は、.def ファイルまたは **__declspec (dllexport)** キーワードを使用してエクスポートするかどうかにかかわらず機能します。

コードを読みやすくするには、 **__declspec (dllimport)** 用のマクロを定義し、マクロを使用してインポートされた各シンボルを宣言します。

```
#define DllImport   __declspec( dllimport )

DllImport int  j;
DllImport void func();
```

**__Declspec (dllimport)** の使用は関数宣言では省略可能ですが、このキーワードを使用すると、コンパイラはより効率的なコードを生成します。 ただし、インポートする実行可能ファイルには、 **__declspec (dllimport)** を使用して、DLL のパブリックデータシンボルおよびオブジェクトにアクセスする必要があります。 DLL を使う場合は、引き続きインポート ライブラリとリンクする必要があることに注意してください。

DLL とクライアント アプリケーションには、同じヘッダー ファイルを使うことができます。 こうする場合は、DLL のビルドとクライアント アプリケーションのビルドの区別を示すために、専用のプリプロセッサ シンボルを使います。 例 :

```
#ifdef _EXPORTING
   #define CLASS_DECLSPEC    __declspec(dllexport)
#else
   #define CLASS_DECLSPEC    __declspec(dllimport)
#endif

class CLASS_DECLSPEC CExampleA : public CObject
{ ... class definition ... };
```

## <a name="what-do-you-want-to-do"></a>作業内容

- [DLL の初期化](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [インライン関数のインポートとエクスポート](importing-and-exporting-inline-functions.md)

- [相互インポート](mutual-imports.md)

## <a name="see-also"></a>参照

[アプリケーションへのインポート](importing-into-an-application.md)
