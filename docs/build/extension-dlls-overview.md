---
title: 拡張 DLL:概要
ms.date: 05/06/2019
helpviewer_keywords:
- AFXDLL library
- MFC DLLs [C++], MFC extension DLLs
- DLLs [C++], extension
- shared DLL versions [C++]
- extension DLLs [C++], about MFC extension DLLs
ms.assetid: eb5e10b7-d615-4bc7-908d-e3e99b7b1d5f
ms.openlocfilehash: ea8e950e28907ea1a4a85c1f39392d5505f08c49
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221361"
---
# <a name="mfc-extension-dlls-overview"></a>MFC 拡張 DLL:概要

MFC 拡張 DLL は、既存の Microsoft Foundation Class ライブラリ クラスから派生した再利用可能なクラスを通常実装する DLL です。 MFC 拡張 DLL は、MFC のダイナミック リンク ライブラリ バージョン (MFC の共有バージョン) を使ってビルドされます。 MFC 拡張 DLL を使用できるのは、MFC の共有バージョンを使ってビルドされた MFC の実行可能ファイル (アプリケーションまたは標準 MFC DLL) のみです。 MFC 拡張 DLL を使うと、MFC から新しいカスタム クラスを派生させ、この拡張バージョンの MFC を、ご自分の DLL を呼び出すアプリケーションに指定できます。

また、拡張 DLL を使うと、アプリケーションと DLL の間で MFC の派生オブジェクトをやり取りすることもできます。 やり取りされるオブジェクトに関連付けられたメンバー関数は、そのオブジェクトが作成されたモジュール内にあります。 これらの関数は MFC の共有 DLL バージョンの使用時に正しくエクスポートされるので、MFC または MFC から派生したオブジェクト ポインターをアプリケーションとそれがお見込む MFC 拡張 DLL 間で自由にやり取りできます。

MFC 拡張 DLL の基本要件を満たす DLL の例については、MFC のサンプルの [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk) に関するページを参照してください。 特に、Testdll1.cpp ファイルおよび Testdll2.cpp ファイルをご確認ください。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [MFC 拡張 DLL の初期化](run-time-library-behavior.md#initializing-extension-dlls)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [MFC 拡張 DLL](extension-dlls.md)

- [レギュラー MFC DLL でのデータベース、OLE、およびソケット MFC 拡張 DLL の使用](using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

- [非 MFC DLL:概要](non-mfc-dlls-overview.md)

- [MFC と静的にリンクされる標準 MFC DLL](regular-dlls-statically-linked-to-mfc.md)

- [MFC と動的にリンクされる標準 MFC DLL](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC DLL の作成](../mfc/reference/mfc-dll-wizard.md)

## <a name="see-also"></a>関連項目

[DLL の種類](kinds-of-dlls.md)
