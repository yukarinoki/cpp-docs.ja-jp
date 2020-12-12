---
description: '詳細情報: カスタム文字列マネージャーの実装 (基本メソッド)'
title: カスタム文字列マネージャー (基本メソッド) の実装
ms.date: 11/04/2016
helpviewer_keywords:
- IAtlStringMgr class, using
ms.assetid: eac5d13e-cbb4-4e82-b01e-f5f2dbcb962a
ms.openlocfilehash: e532312edff16229b6b91eef1d95ae764b70eb5e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166955"
---
# <a name="implementation-of-a-custom-string-manager-basic-method"></a>カスタム文字列マネージャー (基本メソッド) の実装

文字列データのメモリ割り当てスキームをカスタマイズする最も簡単な方法は、ATL に用意されているクラスを使用することです `CAtlStringMgr` が、独自のメモリ割り当てルーチンを提供することです。 のコンストラクターは、 `CAtlStringMgr` 1 つのパラメーター (オブジェクトへのポインター) を受け取ります `IAtlMemMgr` 。 `IAtlMemMgr` は、ヒープへのジェネリックインターフェイスを提供する抽象基本クラスです。 では、インターフェイスを使用して、 `IAtlMemMgr` `CAtlStringMgr` 文字列データの格納に使用されるメモリの割り当て、再割り当て、解放を行います。 インターフェイスを自分で実装するか、 `IAtlMemMgr` ATL に用意されている5つのメモリマネージャークラスのいずれかを使用することができます。 ATL に用意されているメモリマネージャーは、単純に既存のメモリ割り当て機能をラップします。

- [Ccrtheap](../atl/reference/ccrtheap-class.md) 標準 CRT ヒープ関数 ([malloc](../c-runtime-library/reference/malloc.md)、 [free](../c-runtime-library/reference/free.md)、および [realloc](../c-runtime-library/reference/realloc.md)) をラップします。

- [CWin32Heap](../atl/reference/cwin32heap-class.md)[HeapAlloc](/windows/win32/api/heapapi/nf-heapapi-heapalloc)、 [heapfree](/windows/win32/api/heapapi/nf-heapapi-heapfree)、および[heapfree](/windows/win32/api/heapapi/nf-heapapi-heaprealloc)を使用して、Win32 ヒープハンドルをラップします。

- [Clocalheap](../atl/reference/clocalheap-class.md) Win32 Api をラップします: [LocalAlloc](/windows/win32/api/winbase/nf-winbase-localalloc)、 [LocalFree](/windows/win32/api/winbase/nf-winbase-localfree)、および [localrealloc](/windows/win32/api/winbase/nf-winbase-localrealloc)

- [Cglobalheap](../atl/reference/cglobalheap-class.md) Win32 Api ( [GlobalAlloc](/windows/win32/api/winbase/nf-winbase-globalalloc)、 [GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree)、および [globalrealloc](/windows/win32/api/winbase/nf-winbase-globalrealloc)) をラップします。

- [CComHeap](../atl/reference/ccomheap-class.md) COM タスクアロケーター Api をラップします: [CoTaskMemAlloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc)、 [CoTaskMemFree](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree)、および [CoTaskMemRealloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc)

文字列メモリ管理のために、最も役に立つクラスは、 `CWin32Heap` 複数の独立したヒープを作成できることです。 たとえば、文字列に対してのみ個別のヒープを使用する場合は、次のようにします。

[!code-cpp[NVC_ATLMFC_Utilities#180](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_1.cpp)]

このプライベート文字列マネージャーを使用して変数のメモリを管理するには `CString` 、変数のコンストラクターにパラメーターとしてマネージャーへのポインターを渡し `CString` ます。

[!code-cpp[NVC_ATLMFC_Utilities#181](../atl-mfc-shared/codesnippet/cpp/implementation-of-a-custom-string-manager-basic-method_2.cpp)]

## <a name="see-also"></a>関連項目

[CStringT を使用したメモリ管理](../atl-mfc-shared/memory-management-with-cstringt.md)
