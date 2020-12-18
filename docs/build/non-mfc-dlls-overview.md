---
description: '詳細情報: 非 MFC DLL:概要'
title: 非 MFC DLL:概要
ms.date: 11/04/2016
helpviewer_keywords:
- non-MFC DLLs [C++]
- DLLs [C++], non-MFC
ms.assetid: 1ed5d1ee-e20c-47d7-801d-87ea26a73842
ms.openlocfilehash: 2b71653be8a665684b7e79dcb48ac54d86834be0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179838"
---
# <a name="non-mfc-dlls-overview"></a>非 MFC DLL:概要

MFC ではない DLL は内部で MFC を使用しない DLL です。その DLL 内のエクスポートされた関数は、MFC または非 MFC 実行可能ファイルから呼び出すことができます。 通常、関数は標準の C インターフェイスを使用して MFC 以外の DLL からエクスポートされます。

MFC 以外の DLL の詳細については、Windows SDK の「[ダイナミックリンク ライブラリ](/windows/win32/dlls/dynamic-link-libraries)」を参照してください。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [チュートリアル: ダイナミック リンク ライブラリの作成と使用](walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)

- [DLL からのエクスポート](exporting-from-a-dll.md)

- [実行可能ファイルと DLL のリンク](linking-an-executable-to-a-dll.md)

- [DLL の初期化](run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [MFC と静的にリンクされる標準 MFC DLL](regular-dlls-statically-linked-to-mfc.md)

- [MFC と動的にリンクされる標準 MFC DLL](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC 拡張 DLL:概要](extension-dlls-overview.md)

## <a name="see-also"></a>関連項目

[DLL の種類](kinds-of-dlls.md)
