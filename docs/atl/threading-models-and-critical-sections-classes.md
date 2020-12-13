---
description: 詳細については、「スレッドモデルとクリティカルセクションクラス」を参照してください。
title: スレッドモデルとクリティカルセクションクラス (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, critical sections
- ATL, multithreading
- threading [ATL], models
- critical sections
ms.assetid: 759f05ef-6285-4be6-a2cc-78572dd75146
ms.openlocfilehash: 51ad5a5f2f03bfe080395966d0c480615c49a109
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138282"
---
# <a name="threading-models-and-critical-sections-classes"></a>スレッドモデルとクリティカルセクションクラス

次のクラスは、スレッドモデルとクリティカルセクションを定義します。

- [CAtlAutoThreadModule](../atl/reference/catlautothreadmodule-class.md) スレッドプールされたアパートメントモデルの COM サーバーを実装します。

- [CAtlAutoThreadModuleT](../atl/reference/catlautothreadmodulet-class.md) スレッドプールされたアパートメントモデル COM サーバーを実装するためのメソッドを提供します。

- [CComMultiThreadModel](../atl/reference/ccommultithreadmodel-class.md) 変数をインクリメントおよびデクリメントするためのスレッドセーフなメソッドを提供します。 クリティカルセクションを提供します。

- [CComMultiThreadModelNoCS](../atl/reference/ccommultithreadmodelnocs-class.md) 変数をインクリメントおよびデクリメントするためのスレッドセーフなメソッドを提供します。 はクリティカルセクションを提供しません。

- [CComSingleThreadModel](../atl/reference/ccomsinglethreadmodel-class.md) 変数をインクリメントおよびデクリメントするためのメソッドを提供します。 はクリティカルセクションを提供しません。

- [CComObjectThreadModel](../atl/reference/atl-typedefs.md#ccomobjectthreadmodel) 1つのオブジェクトクラスに対して適切なスレッドモデルクラスを決定します。

- [CComGlobalsThreadModel](../atl/reference/atl-typedefs.md#ccomglobalsthreadmodel) グローバルに使用できるオブジェクトに対して、適切なスレッドモデルクラスを決定します。

- [CComAutoCriticalSection](../atl/reference/ccomautocriticalsection-class.md) クリティカルセクションを取得および解放するためのメソッドを格納します。 クリティカルセクションが自動的に初期化されます。

- [CComCriticalSection](../atl/reference/ccomcriticalsection-class.md) クリティカルセクションを取得および解放するためのメソッドを格納します。 クリティカルセクションを明示的に初期化する必要があります。

- [CComFakeCriticalSection](../atl/reference/ccomfakecriticalsection-class.md) クリティカルセクションを指定せずに、のメソッドをミラー化し `CComCriticalSection` ます。 のメソッドは `CComFakeCriticalSection` 何も行いません。

- [CRTThreadTraits](../atl/reference/crtthreadtraits-class.md) CRT スレッドの作成関数を提供します。 スレッドが CRT 関数を使用する場合は、このクラスを使用します。

- [Win32ThreadTraits](../atl/reference/win32threadtraits-class.md) Windows スレッドの作成関数を提供します。 スレッドが CRT 関数を使用しない場合は、このクラスを使用します。

## <a name="see-also"></a>関連項目

[クラスの概要](../atl/atl-class-overview.md)
