---
title: 'OLE の背景知識 : MFC における実装'
ms.date: 11/04/2016
f1_keywords:
- IMarshall
- IMoniker
helpviewer_keywords:
- MFC libraries, implementing
- OLE MFC library implementation
- OLE IMarshal interface
- IMoniker interface, MFC
- IMarshall class [MFC]
- OLE, compound files
- OLE IMoniker interface
- OLE IUnknown
ms.assetid: 2b67016a-d78e-4d60-925f-c28ec8fb6180
ms.openlocfilehash: 25c98c3683a8656bb5188f22d0464d25a4901f49
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364532"
---
# <a name="ole-background-mfc-implementation"></a>OLE の背景知識 : MFC における実装

OLE API のサイズと複雑さにより、OLE アプリケーションを直接呼び出すと、非常に時間がかかります。 OLE の Microsoft Foundation クラス ライブラリの実装の目的は、フル機能の OLE 対応アプリケーションを作成するために必要な作業量を削減することです。

この資料では、MFC の内部に実装されていない OLE API の部分について説明します。 また、実装される内容が Windows SDK の OLE セクションにどのように対応するのかについても説明します。

## <a name="portions-of-ole-not-implemented-by-the-class-library"></a><a name="_core_portions_of_ole_not_implemented_by_the_class_library"></a>クラス ライブラリによって実装されない OLE の一部

OLE のいくつかのインターフェイスと機能は、MFC によって直接提供されていません。 これらの機能を使用する場合は、OLE API を直接呼び出すことができます。

IMoniker インターフェイス`IMoniker`インターフェイスはクラス ライブラリ (たとえば、`COleServerItem`クラス) によって実装されますが、以前はプログラマに公開されていません。 このインターフェイスの詳細については、Windows SDK の OLE セクションの「OLE モニカーの実装」を参照してください。 ただし、クラス[CMonikerFile](../mfc/reference/cmonikerfile-class.md)および[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)も参照してください。

IUnknown インターフェイスと IMarshal`IUnknown`インターフェイス インターフェイスはクラス ライブラリによって実装されますが、プログラマには公開されません。 インターフェイス`IMarshal`はクラス ライブラリによって実装されませんが、内部的に使用されます。 クラス ライブラリを使用して作成されたオートメーション サーバーには、マーシャリング機能が既に組み込まれています。

Docfiles (複合ファイル) 複合ファイルは、クラス ライブラリで部分的にサポートされています。 作成を超えて複合ファイルを直接操作する関数はサポートされていません。 MFC では`COleFileStream`、クラスを使用して、標準のファイル関数を使用したストリームの操作をサポートします。 詳細については、「[コンテナ: 複合ファイル](../mfc/containers-compound-files.md)」を参照してください。

インプロセス サーバーとオブジェクト ハンドラー インプロセス サーバーとオブジェクト ハンドラーを使用すると、ビジュアル編集データまたはフル コンポーネント オブジェクト モデル (COM) オブジェクトをダイナミック リンク ライブラリ (DLL) に実装できます。 これを行うには、OLE API を直接呼び出して DLL を実装します。 ただし、オートメーション サーバーを作成していて、サーバーにユーザー インターフェイスがない場合は、AppWizard を使用してサーバーをインプロセス サーバーにし、完全に DLL に配置できます。 これらのトピックの詳細については、「オートメーション[サーバー](../mfc/automation-servers.md)」を参照してください。

> [!TIP]
> オートメーション サーバーを実装する最も簡単な方法は、DLL に配置することです。 MFC では、この方法がサポートされています。

OLE インターフェイスを実装する方法の詳細については、MFC テクニカル ノート[38、39、](../mfc/tn039-mfc-ole-automation-implementation.md)および[38](../mfc/tn038-mfc-ole-iunknown-implementation.md) [40](../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md)を参照してください。

## <a name="see-also"></a>関連項目

[OLE の背景知識](../mfc/ole-background.md)<br/>
[OLE の背景知識 : 実装の方法](../mfc/ole-background-implementation-strategies.md)
