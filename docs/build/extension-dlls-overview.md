---
title: 拡張 Dll:概要
ms.date: 11/04/2016
helpviewer_keywords:
- AFXDLL library
- MFC DLLs [C++], MFC extension DLLs
- DLLs [C++], extension
- shared DLL versions [C++]
- extension DLLs [C++], about MFC extension DLLs
ms.assetid: eb5e10b7-d615-4bc7-908d-e3e99b7b1d5f
ms.openlocfilehash: 0ad5c82d72a3cd9b4801274aefd40d96afdbcdd1
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57425056"
---
# <a name="mfc-extension-dlls-overview"></a>MFC 拡張 Dll:概要

MFC 拡張 DLL は、通常は既存の Microsoft Foundation Class ライブラリ クラスから派生した再利用可能なクラスを実装する DLL です。 MFC 拡張 Dll は、MFC (MFC の共有バージョンとも呼ばれます) のダイナミック リンク ライブラリのバージョンを使用して構築されます。 のみ MFC の実行可能ファイル (アプリケーションまたはレギュラー MFC Dll) は MFC の共有バージョンを使用して作成するには、MFC 拡張 DLL を使用できます。 MFC 拡張 DLL では、MFC から新しいカスタム クラスを派生でき、この拡張バージョンの MFC DLL を呼び出すアプリケーションを提供できます。

また、拡張 DLL を使うと、アプリケーションと DLL の間で MFC の派生オブジェクトをやり取りすることもできます。 やり取りされるオブジェクトに関連付けられたメンバー関数は、そのオブジェクトが作成されたモジュール内にあります。 MFC を自由に渡すことができますので、MFC の共有 DLL バージョンを使用する場合、これらの関数が正しくエクスポート、または MFC の派生オブジェクトのポインター、アプリケーションと MFC 拡張 Dll が読み込まれます。

MFC 拡張 DLL の基本的な要件を実現する DLL の例は、MFC のサンプルを参照してください。 [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk)します。 具体的には、Testdll1.cpp と Testdll2.cpp ファイルを確認します。

AFXDLL という用語は、Visual C のドキュメントでは使用されなくに注意してください。 MFC 拡張 DLL は、前者の AFXDLL と同じ特性を持ちます。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [MFC 拡張 DLL を初期化します。](../build/run-time-library-behavior.md#initializing-extension-dlls)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [MFC 拡張 DLL](../build/extension-dlls.md)

- [レギュラー MFC DLL でのデータベース、OLE、およびソケット MFC 拡張 DLL の使用](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

- [非 MFC DLL:概要](../build/non-mfc-dlls-overview.md)

- [MFC と静的にリンクされるレギュラー MFC の Dll](../build/regular-dlls-statically-linked-to-mfc.md)

- [MFC と動的にリンクされるレギュラー MFC の Dll](../build/regular-dlls-dynamically-linked-to-mfc.md)

- [MFC DLL を作成します。](../mfc/reference/mfc-dll-wizard.md)

## <a name="see-also"></a>関連項目

[DLL の種類](../build/kinds-of-dlls.md)
