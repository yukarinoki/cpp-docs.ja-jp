---
title: シリアル化 (C + + CLI) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- serialization [C++]
- SerializableAttribute class, managed applications
- NonSerializedAttribute class, managed applications
- managed code [C++], serializing
- .NET Framework [C++], serialization
- serialization [C++], about serialization
ms.assetid: 869010ca-74e1-4989-b409-4643cdb94084
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f4a410da74c37ee722c04f21e2cde906b9d061d2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="serialization-ccli"></a>シリアル化 (C++/CLI)
シリアル化 (オブジェクトまたは永続的なメディアにメンバーの状態を保存するプロセス) のマネージ クラス (個々 のフィールドまたはプロパティを含む) でサポートされて、<xref:System.SerializableAttribute>と<xref:System.NonSerializedAttribute>クラスです。  
  
## <a name="remarks"></a>コメント  
 適用、 **SerializableAttribute**クラス全体をシリアル化またはだけに特定のフィールドまたはプロパティをマネージ クラスの部分をシリアル化を適用するマネージ クラスへのカスタム属性です。 使用して、 **NonSerializedAttribute**シリアル化の対象から除外フィールドやマネージ クラスのプロパティにカスタム属性です。  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  
 次の例では、クラス`MyClass`(プロパティと`m_nCount`) シリアル化可能としてマークされています。 ただし、`m_nData`によって示されるプロパティはシリアル化されません、 **NonSerialized**カスタム属性。  
  
### <a name="code"></a>コード  
  
```  
// serialization_and_mcpp.cpp  
// compile with: /LD /clr  
using namespace System;  
  
[ Serializable ]  
public ref class MyClass {  
public:  
   int m_nCount;  
private:  
   [ NonSerialized ]  
   int m_nData;  
};  
```  
  
### <a name="comments"></a>コメント  
 その「短い名前」を使用して両方の属性を参照できることに注意してください (**Serializable**と**NonSerialized**)。 詳細についてはこの[属性の適用](/dotnet/standard/attributes/applying-attributes)です。  
  
## <a name="see-also"></a>関連項目  
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)