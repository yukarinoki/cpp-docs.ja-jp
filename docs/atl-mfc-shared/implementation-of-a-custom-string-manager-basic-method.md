---
title: 実装のカスタム文字列マネージャー (基本的な方法) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IAtlStringMgr class, using
ms.assetid: eac5d13e-cbb4-4e82-b01e-f5f2dbcb962a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 259f9533747b266f0be0a782cdc94c98f167d2d2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32355726"
---
# <a name="implementation-of-a-custom-string-manager-basic-method"></a>実装のカスタム文字列マネージャー (基本的な方法)
文字列データは、ATL 指定を使用するは、メモリの割り当て方法をカスタマイズする最も簡単な方法**CAtlStringMgr**クラスが、独自のメモリ割り当てルーチンを提供します。 コンス トラクター **CAtlStringMgr** 1 つのパラメーターを受け取る: へのポインター、`IAtlMemMgr`オブジェクト。 `IAtlMemMgr` ヒープへの汎用インターフェイスを提供する抽象基本クラス。 使用して、 `IAtlMemMgr` 、インターフェイス、 **CAtlStringMgr** 、再割り当てすると、メモリ割り当てし、解放、文字列データを格納するために使用します。 いずれかを実装することができます、`IAtlMemMgr`インターフェイスを自分で、または 5 つの ATL に用意されているメモリ マネージャー クラスのいずれかを使用します。 ATL に用意されているメモリ マネージャーは、単に既存のメモリ割り当て機能をラップします。  
  
-   [CCRTHeap](../atl/reference/ccrtheap-class.md) 、標準 CRT ヒープ関数をラップ ([malloc](../c-runtime-library/reference/malloc.md)、[空き](../c-runtime-library/reference/free.md)、および[realloc](../c-runtime-library/reference/realloc.md))  
  
-   [CWin32Heap](../atl/reference/cwin32heap-class.md)を使用して Win32 ヒープを処理するラップ[HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597)、 [HeapFree](http://msdn.microsoft.com/library/windows/desktop/aa366701)、および[HeapRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366704)  
  
-   [CLocalHeap](../atl/reference/clocalheap-class.md) Win32 Api をラップ: [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723)、 [LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730)、および[LocalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366742)  
  
-   [CGlobalHeap](../atl/reference/cglobalheap-class.md) Win32 Api をラップ: [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574)、 [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579)、および[GlobalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366590)です。  
  
-   [CComHeap](../atl/reference/ccomheap-class.md) COM タスク アロケーター Api をラップ: [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727)、 [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722)、および[CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280)  
  
 最も役に立つのクラスは、文字列メモリの管理を目的として`CWin32Heap`のため、複数の独立したヒープを作成することができます。 たとえば、文字列だけに独立したヒープを使用する場合は、次のような操作をする可能性があります。  
  
 [!code-cpp[NVC_ATLMFC_Utilities#180](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_1.cpp)]  
  
 このプライベート文字列マネージャーを使用して、用のメモリを管理する、`CString`変数にパラメーターとして、マネージャーへのポインターをパス、`CString`変数のコンス トラクター。  
  
 [!code-cpp[NVC_ATLMFC_Utilities#181](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CStringT によるメモリ管理](../atl-mfc-shared/memory-management-with-cstringt.md)

