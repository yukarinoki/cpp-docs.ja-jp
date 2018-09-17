---
title: '非 MFC Dll: 概要 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- non-MFC DLLs [C++]
- DLLs [C++], non-MFC
ms.assetid: 1ed5d1ee-e20c-47d7-801d-87ea26a73842
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30a6fef31dee39cc6337b9b8b7dd3b66ee3adb67
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702586"
---
# <a name="non-mfc-dlls-overview"></a>非 MFC DLL: 概要

非 MFC DLL が内部的には、MFC を使わない DLL と、MFC または非 MFC の実行可能ファイル、DLL からエクスポートされた関数を呼び出すことができます。 関数から、非 MFC DLL 標準の C インターフェイスを使用して、通常はエクスポートされます。

非 MFC Dll の詳細については、次を参照してください。[ダイナミック リンク ライブラリ](https://msdn.microsoft.com/library/windows/desktop/ms682589)Windows SDK に含まれています。

## <a name="what-do-you-want-to-do"></a>実行する操作

- [チュートリアル: を作成して、ダイナミック リンク ライブラリを使用します。](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)

- [DLL からのエクスポートします。](../build/exporting-from-a-dll.md)

- [実行可能ファイルと DLL のリンク](../build/linking-an-executable-to-a-dll.md)

- [DLL を初期化します。](../build/run-time-library-behavior.md#initializing-a-dll)

## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [MFC と静的にリンクされるレギュラー MFC の Dll](../build/regular-dlls-statically-linked-to-mfc.md)

- [MFC と動的にリンクされるレギュラー MFC の Dll](../build/regular-dlls-dynamically-linked-to-mfc.md)

- [MFC 拡張 DLL: 概要](../build/extension-dlls-overview.md)

## <a name="see-also"></a>関連項目

[DLL の種類](../build/kinds-of-dlls.md)