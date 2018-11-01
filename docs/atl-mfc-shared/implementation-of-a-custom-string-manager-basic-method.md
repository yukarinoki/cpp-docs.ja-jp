---
title: カスタム文字列マネージャーの実装 (基本方法)
ms.date: 11/04/2016
helpviewer_keywords:
- IAtlStringMgr class, using
ms.assetid: eac5d13e-cbb4-4e82-b01e-f5f2dbcb962a
ms.openlocfilehash: 4e3ffcdcd034fea81734aaeb87e4c33d81647f66
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537815"
---
# <a name="implementation-of-a-custom-string-manager-basic-method"></a>カスタム文字列マネージャーの実装 (基本方法)

文字列データは、ATL に使用するは、メモリの割り当て方法をカスタマイズする最も簡単な方法は、`CAtlStringMgr`クラスしますが、自身のメモリ割り当てルーチンを提供します。 コンス トラクター `CAtlStringMgr` 1 つのパラメーターを受け取る: へのポインター、`IAtlMemMgr`オブジェクト。 `IAtlMemMgr` ヒープにジェネリック インターフェイスを提供する抽象基本クラスです。 使用して、 `IAtlMemMgr` 、インターフェイス、`CAtlStringMgr`割り当て、再割り当て、および文字列データの格納に使用されるメモリを解放します。 実装することができます、`IAtlMemMgr`インターフェイスを自分で、または ATL に用意されているメモリの 5 つの manager クラスのいずれかを使用します。 ATL に用意されているメモリ マネージャーは、単に既存のメモリ割り当て機能をラップします。

- [CCRTHeap](../atl/reference/ccrtheap-class.md) 、標準 CRT ヒープ関数をラップします ([malloc](../c-runtime-library/reference/malloc.md)、[無料](../c-runtime-library/reference/free.md)、および[realloc](../c-runtime-library/reference/realloc.md))

- [CWin32Heap](../atl/reference/cwin32heap-class.md)を使用して Win32 ヒープを処理するラップ[HeapAlloc](/windows/desktop/api/heapapi/nf-heapapi-heapalloc)、[選択肢](/windows/desktop/api/heapapi/nf-heapapi-heapfree)、および[HeapRealloc](/windows/desktop/api/heapapi/nf-heapapi-heaprealloc)

- [CLocalHeap](../atl/reference/clocalheap-class.md) Win32 Api をラップします[LocalAlloc](/windows/desktop/api/winbase/nf-winbase-localalloc)、 [LocalFree](/windows/desktop/api/winbase/nf-winbase-localfree)、および[LocalRealloc。](/windows/desktop/api/winbase/nf-winbase-localrealloc)

- [CGlobalHeap](../atl/reference/cglobalheap-class.md) Win32 Api をラップします。 [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc)、 [GlobalFree](/windows/desktop/api/winbase/nf-winbase-globalfree)、および[GlobalRealloc](/windows/desktop/api/winbase/nf-winbase-globalrealloc)します。

- [CComHeap](../atl/reference/ccomheap-class.md) COM タスク アロケーターの Api をラップします[CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc)、 [CoTaskMemFree](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemfree)、および[CoTaskMemRealloc。](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemrealloc)

最も役に立つ、クラスは、文字列のメモリ管理するために`CWin32Heap`のため、複数の独立したヒープを作成することができます。 たとえば、文字列だけに独立したヒープを使用する場合は、次のような操作をする可能性があります。

[!code-cpp[NVC_ATLMFC_Utilities#180](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_1.cpp)]

このプライベート文字列 manager を使用して、メモリを管理する、`CString`変数へのパラメーターとして、マネージャーにポインターを渡す、`CString`変数のコンス トラクター。

[!code-cpp[NVC_ATLMFC_Utilities#181](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_2.cpp)]

## <a name="see-also"></a>関連項目

[CStringT によるメモリ管理](../atl-mfc-shared/memory-management-with-cstringt.md)

