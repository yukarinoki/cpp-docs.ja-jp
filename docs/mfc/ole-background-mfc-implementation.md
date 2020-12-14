---
description: '詳細については、「OLE バックグラウンド: MFC の実装」を参照してください。'
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
ms.openlocfilehash: 81b62fc1ff704a8a0f34bfd1ac864142720b3864
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343543"
---
# <a name="ole-background-mfc-implementation"></a>OLE の背景知識 : MFC における実装

未加工の OLE API のサイズと複雑さのために、OLE アプリケーションを直接呼び出すと、非常に時間がかかることがあります。 OLE の Microsoft Foundation Class ライブラリ実装の目的は、フル機能の OLE 対応アプリケーションを作成するために必要な作業量を削減することです。

この記事では、MFC 内部で実装されていない OLE API の部分について説明します。 また、実装されているが Windows SDK の OLE セクションにマップされる方法についても説明します。

## <a name="portions-of-ole-not-implemented-by-the-class-library"></a><a name="_core_portions_of_ole_not_implemented_by_the_class_library"></a> クラスライブラリによって実装されていない OLE の部分

OLE のいくつかのインターフェイスと機能は、MFC によって直接提供されるわけではありません。 これらの機能を使用する場合は、OLE API を直接呼び出すことができます。

IMoniker インターフェイス `IMoniker` インターフェイスはクラスライブラリ (たとえば、クラス) によって実装されていますが、 `COleServerItem` 以前はプログラマに公開されていません。 このインターフェイスの詳細については、「Windows SDK の OLE セクションでの OLE モニカーの実装」を参照してください。 ただし、「 [CMonikerFile](reference/cmonikerfile-class.md) and [CAsyncMonikerFile](reference/casyncmonikerfile-class.md)クラス」も参照してください。

IUnknown インターフェイスと IMarshal インターフェイス `IUnknown` インターフェイスはクラスライブラリによって実装されますが、プログラマには公開されません。 `IMarshal`インターフェイスはクラスライブラリによって実装されていませんが、内部で使用されます。 クラスライブラリを使用して構築されたオートメーションサーバーには、既にマーシャリング機能が組み込まれています。

Docfiles (複合ファイル) 複合ファイルは、クラスライブラリによって部分的にサポートされています。 複合ファイルを作成以外に直接操作する関数はサポートされていません。 MFC では、クラスを使用し `COleFileStream` て、標準ファイル関数を使用したストリームの操作をサポートします。 詳細については、「 [コンテナー: 複合ファイル](containers-compound-files.md)」を参照してください。

In-Process サーバーとオブジェクトハンドラーのインプロセスサーバーおよびオブジェクトハンドラーを使用すると、ダイナミックリンクライブラリ (DLL) でビジュアル編集データまたは完全なコンポーネントオブジェクトモデル (COM) オブジェクトを実装できます。 これを行うには、OLE API を直接呼び出して DLL を実装します。 ただし、オートメーションサーバーを作成しているときに、サーバーにユーザーインターフェイスがない場合は、AppWizard を使用してサーバーをインプロセスサーバーにし、DLL に完全に配置できます。 これらのトピックの詳細については、「 [Automation Servers](automation-servers.md)」を参照してください。

> [!TIP]
> オートメーションサーバーを実装する最も簡単な方法は、DLL に配置することです。 MFC では、この方法がサポートされています。

Microsoft Foundation OLE クラスが OLE インターフェイスを実装する方法の詳細については、「MFC テクニカルノート [38](tn038-mfc-ole-iunknown-implementation.md)、 [39](tn039-mfc-ole-automation-implementation.md)、および [40](tn040-mfc-ole-in-place-resizing-and-zooming.md)」を参照してください。

## <a name="see-also"></a>関連項目

[OLE の背景](ole-background.md)<br/>
[OLE の背景知識: 実装方法](ole-background-implementation-strategies.md)
