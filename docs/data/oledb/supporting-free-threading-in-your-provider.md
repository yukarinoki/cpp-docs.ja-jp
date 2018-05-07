---
title: プロバイダーでのフリー スレッドのサポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, multithreaded
- threading [C++], providers
ms.assetid: a91270dc-cdf9-4855-88e7-88a54be7cbe8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9c61aea0fec1f6d808a0a34ee74bd0ce2d399a5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="supporting-free-threading-in-your-provider"></a>プロバイダーでのフリー スレッドのサポート
すべての OLE DB プロバイダー クラスはスレッド セーフである、およびレジストリ エントリはそれに従って設定されます。 高レベルのマルチ ユーザー環境でのパフォーマンスを提供するのに役立つフリー スレッドをサポートすることをお勧めします。 スレッド セーフである、プロバイダーに保つためには、コードが正常にブロックされていることを確認する必要があります。 書き込みまたはデータを格納するたびに、重要なセクションを使用してアクセスをブロックする必要があります。  
  
 各 OLE DB プロバイダー テンプレート オブジェクトには、独自の重要なセクションがあります。 ブロッキングを簡単にするには、作成する新しいクラスのそれぞれが、テンプレート クラスは、親クラスをする必要があります引数として名前。  
  
 次の例では、コードをブロックする方法を示します。  
  
```  
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
  
 重要なセクションを保護する方法の詳細についての`Lock`と`Unlock`を参照してください[マルチ スレッド: 同期クラスを使用する方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)です。  
  
 任意のメソッド オーバーライドすることも確認する必要があります (など`Execute`) スレッド セーフです。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)