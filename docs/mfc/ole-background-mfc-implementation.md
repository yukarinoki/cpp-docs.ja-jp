---
title: 'OLE の背景知識: MFC における実装 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- IMarshall
- IMoniker
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d77d603c198adad2ca2c827c355ff8f6808bff66
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930327"
---
# <a name="ole-background-mfc-implementation"></a>OLE の背景知識 : MFC における実装
によりのサイズと複雑さ生 OLE API、OLE アプリケーションを作成するには、直接呼び出すなる可能性が非常に時間がかかります。 OLE の Microsoft Foundation Class ライブラリの実装の目的は、全機能を備えた、OLE 対応のアプリケーションを作成するために必要な作業の量を削減します。  
  
 この記事では、MFC の内部実装されていない OLE API の部分について説明します。 説明では、新機能は実装にマップする方法、Windows SDK の OLE セクションについても説明します。  
  
##  <a name="_core_portions_of_ole_not_implemented_by_the_class_library"></a> クラス ライブラリで実装されていない OLE の部分  
 いくつかのインターフェイスと OLE の機能が直接指定されていない MFC でします。 これらの機能を使用する場合は、直接 OLE API を呼び出すことができます。  
  
 IMoniker インターフェイス  
 `IMoniker`インターフェイスは、クラス ライブラリによって実装 (たとえば、`COleServerItem`クラス) が以前プログラマに公開されていません。 このインターフェイスの詳細については、OLE モニカーの実装、Windows SDK の OLE セクションを参照してください。 ただし、クラスを参照[CMonikerFile](../mfc/reference/cmonikerfile-class.md)と[CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)です。  
  
 IUnknown と IMarshal インターフェイス  
 `IUnknown`インターフェイスは、クラス ライブラリによって実装されるは、プログラマに公開されていません。 `IMarshal`インターフェイスは、クラス ライブラリによって実装されていませんが、内部的に使用します。 クラス ライブラリを使用して既に作成したオートメーション サーバーでは、マーシャ リングに組み込まれている機能があります。  
  
 Docfiles (複合ファイル)  
 複合ファイルは、クラス ライブラリによって部分的にサポートされます。 複合ファイルの作成以外を直接操作する関数がサポートされていません。 MFC クラスを使用して`COleFileStream`ファイルの標準的な関数を使用して、ストリームの操作をサポートするためにします。 詳細については、記事を参照してください。[コンテナー: 複合ファイル](../mfc/containers-compound-files.md)です。  
  
 インプロセス サーバーとオブジェクト ハンドラー  
 インプロセス サーバーおよびオブジェクト ハンドラーは、データのビジュアル編集またはダイナミック リンク ライブラリ (DLL) ですべてのコンポーネント オブジェクト モデル (COM) オブジェクトの実装を使用できます。 これを行うには、OLE API を直接呼び出すことによって、DLL を実装できます。 ただし、オートメーション サーバーを作成しているユーザー インターフェイスを持っていない場合は、サーバーがインプロセス サーバーを行い、DLL に完全に移行 AppWizard を使用できます。 これらのトピックの詳細については、次を参照してください。[オートメーション サーバー](../mfc/automation-servers.md)です。  
  
> [!TIP]
>  オートメーション サーバーを実装する最も簡単な方法では、DLL に配置することです。 MFC には、この方法がサポートしています。  
  
 Microsoft Foundation OLE クラスが OLE インターフェイスを実装する方法の詳細については、MFC テクニカル ノートを参照してください。 [38](../mfc/tn038-mfc-ole-iunknown-implementation.md)、 [39](../mfc/tn039-mfc-ole-automation-implementation.md)、および[40](../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md)です。  
  
## <a name="see-also"></a>関連項目  
 [OLE の背景知識](../mfc/ole-background.md)   
 [OLE の背景知識: 実装の方法](../mfc/ole-background-implementation-strategies.md)

