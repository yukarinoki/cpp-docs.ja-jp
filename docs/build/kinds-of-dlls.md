---
title: DLL の種類
ms.date: 05/06/2019
helpviewer_keywords:
- MFC DLLs [C++], types
- DLLs [C++], types
- DLLs [C++], MFC
ms.assetid: f6a30db9-6138-4b2c-90cc-a17855e499a6
ms.openlocfilehash: dae44d2dd39597420ce2a2c4e1642e8a7f0784e2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328502"
---
# <a name="kinds-of-dlls"></a>DLL の種類

ここで説明する情報は、ビルドする DLL の種類を決定するときの参考になります。

## <a name="different-kinds-of-dlls-available"></a><a name="_core_the_different_kinds_of_dlls_available_with_visual_c.2b2b"></a>さまざまな種類の DLL が使用可能

Visual Studio を使用すると、C または C++ で、MFC (MFC) ライブラリを使用しない Win32 DLL をビルドできます。 Win32 アプリケーション ウィザードでは、非 MFC DLL プロジェクトを作成できます。

MFC DLL ウィザードでは、スタティック リンク ライブラリでも、多くの DLL でも、MFC ライブラリ自体を利用できます。 DLL が MFC を使用している場合、Visual Studio は 3 つの異なる DLL 開発シナリオをサポートしています。

- MFC を静的にリンクする標準 MFC DLL をビルドする

- MFC を動的にリンクする標準 MFC DLL をビルドする

- 常に MFC と動的にリンクする MFC 拡張 DLLをビルド

### <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [非 MFC DLL: 概要](non-mfc-dlls-overview.md)

- [MFC に静的にリンクされた標準 MFC DLL](regular-dlls-statically-linked-to-mfc.md)

- [MFC と動的にリンクされる標準 MFC DLL](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC 拡張 DLL: 概要](extension-dlls-overview.md)

- [使用する DLL の決定](#_core_which_kind_of_dll_to_use)

## <a name="deciding-which-kind-of-dll-to-use"></a><a name="_core_which_kind_of_dll_to_use"></a>使用する DLL の種類を決定する

DLL が MFC を使用していない場合は、Visual Studio を使用して非 MFC Win32 DLL をビルドします。 リンクの形態が静的か動的かにかかわらず、MFC とリンクする DLL は、ディスク領域とメモリをかなり使用します。 実際に MFC を使わない DLL は、MFC とリンクしないでください。

DLL が MFC を使用する場合、MFC または非 MFC アプリケーションで使用する場合は、MFC に動的にリンクする通常の MFC DLL か、MFC に静的にリンクする標準 MFC DLL をビルドする必要があります。 ほとんどの場合、DLL のファイル サイズが大幅に小さくなり、共有バージョンの MFC を使用するメモリの節約が大幅に行われるため、MFC に動的にリンクする通常の MFC DLL を使用する必要があります。 MFC と静的にリンクする場合は、MFC ライブラリ コードの専用コピーを読み込むために、DLL のファイル サイズは大きくなり、余分なメモリを使用する可能性があります。

動的リンクの場合には MFC 自体をリンクする必要がないため、ビルド処理は静的にリンクされる DLL よりも動的にリンクされる DLL の方が高速です。 この傾向は、リンカーがデバッグ情報を圧縮する必要があるデバッグ ビルドについて特に顕著になります。 デバッグ情報を既に含む DLL とリンクすることによって、DLL 内に圧縮されるデバッグ情報が少なくなります。

MFC との動的リンクの欠点として、MFCx0.dll と Msvcrxx.dll (または同様のファイル) という共有 DLL を一緒に配布する必要性が生じる点を挙げることができます。 MFC DLL の再配布は自由ですが、セットアップ プログラムで DLL をインストールする必要があります。 さらに、プログラムと MFC DLL 自体の双方が使用する C ランタイム ライブラリを含む Msvcrxx.dll も同梱する必要があります。

DLL が MFC 実行可能ファイルでのみ使用される場合は、通常の MFC DLL または MFC 拡張 DLL をビルドするかの選択ができます。 DLL が既存の MFC クラスから派生した再利用可能なクラスを実装している場合、またはアプリケーションと DLL の間で MFC 派生オブジェクトを渡す必要がある場合は、MFC 拡張 DLL をビルドする必要があります。

MFC と動的にリンクされる DLL では、DLL と共に MFC DLL を再配布することもあります。 このアーキテクチャでは、使用ディスク領域が抑制され、メモリの使用も最小化されるため、複数の実行可能ファイル間でクラス ライブラリを共有する場合に特に便利です。

### <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください

- [非 MFC DLL: 概要](non-mfc-dlls-overview.md)

- [MFC に静的にリンクされた標準 MFC DLL](regular-dlls-statically-linked-to-mfc.md)

- [MFC と動的にリンクされる標準 MFC DLL](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC 拡張 DLL: 概要](extension-dlls-overview.md)

## <a name="see-also"></a>関連項目

[Visual Studio での C/C++ Dll の作成](dlls-in-visual-cpp.md)
