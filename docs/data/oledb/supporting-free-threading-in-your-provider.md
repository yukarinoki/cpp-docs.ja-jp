---
title: プロバイダーでのフリー スレッドのサポート
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB providers, multithreaded
- threading [C++], providers
ms.assetid: a91270dc-cdf9-4855-88e7-88a54be7cbe8
ms.openlocfilehash: 50e05b70a782dd343031443540790697e980c994
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209548"
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

`Lock` と `Unlock`で重要なセクションを保護する方法の詳細については、「[マルチスレッド: 同期クラスの使用方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)」を参照してください。

オーバーライドするメソッド (`Execute`など) がスレッドセーフであることを確認します。

## <a name="see-also"></a>参照

[OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)
