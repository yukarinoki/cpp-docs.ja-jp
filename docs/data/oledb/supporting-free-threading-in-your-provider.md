---
description: 詳細については、「プロバイダーでのフリースレッドのサポート」を参照してください。
title: プロバイダーでのフリー スレッドのサポート
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB providers, multithreaded
- threading [C++], providers
ms.assetid: a91270dc-cdf9-4855-88e7-88a54be7cbe8
ms.openlocfilehash: 4f6785dd85ae043ce0ee74c1dda4fa365c566729
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286476"
---
# <a name="supporting-free-threading-in-your-provider"></a>プロバイダーでのフリー スレッドのサポート

OLE DB プロバイダークラスはすべてスレッドセーフであり、それに応じてレジストリエントリが設定されます。 マルチユーザーの状況で高レベルのパフォーマンスを実現するために、無料のスレッド処理をサポートすることをお勧めします。 プロバイダーをスレッドセーフに保つために、コードが適切にブロックされていることを確認する必要があります。 データを書き込んだり格納したりするたびに、重要なセクションでアクセスをブロックする必要があります。

各 OLE DB プロバイダーテンプレートオブジェクトには、独自のクリティカルセクションがあります。 ブロックを簡単にするために、作成する各新しいクラスは、親クラス名を引数として受け取るテンプレートクラスである必要があります。

次の例は、コードをブロックする方法を示しています。

```cpp
template <class T>
class CMyObject<T> : public...

HRESULT MyObject::MyMethod(void)
{
   T* pT = (T*)this;      // this gets the parent class

// You don't need to do anything if you are only reading information

// If you want to write information, do the following:
   pT->Lock();         // engages critical section in the object
   ...;                // write whatever information you wish
   pT->Unlock();       // disengages the critical section
}
```

およびで重要なセクションを保護する方法の詳細について `Lock` `Unlock` は、「 [マルチスレッド: 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)」を参照してください。

オーバーライドするメソッド (など) がスレッドセーフであることを確認し `Execute` ます。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダーテンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)
