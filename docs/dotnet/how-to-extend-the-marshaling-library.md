---
title: '方法: マーシャ リング ライブラリを拡張 |Microsoft ドキュメント'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Marshaling Library, extending
ms.assetid: 4c4a56d7-1d44-4118-b85f-f9686515e6e9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6f6503cbb0006c0c8b2e1ed113a798a23ac2ff55
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-extend-the-marshaling-library"></a>方法: マーシャリング ライブラリを拡張する
このトピックでは、データ型間の複数の変換を提供する、マーシャ リング ライブラリを拡張する方法について説明します。 ユーザーは、ライブラリによってサポートされていないデータ変換のマーシャ リング ライブラリを拡張できます。  
  
 2 つの方法の有無にかかわらずのいずれかでマーシャ リング ライブラリを拡張することができます、 [marshal_context クラス](../dotnet/marshal-context-class.md)です。 確認、[概要の C++ におけるマーシャ リング](../dotnet/overview-of-marshaling-in-cpp.md)のトピックを新しい変換がコンテキストを必要とするかどうかを確認します。  
  
 どちらの場合は、まず新しいマーシャ リング変換のファイルを作成する必要があります。 標準のマーシャ リング ライブラリ ファイルの整合性を保つようにします。 別のコンピューターまたは別のプログラマのプロジェクトに移植する場合は、プロジェクトの残りの部分と共に新しいマーシャ リング ファイルをコピーする必要があります。 この方法では、プロジェクトを受け取るユーザーは、新しい変換を受信するが保証されますされ、すべてのライブラリ ファイルを変更する必要はありません。  
  
### <a name="to-extend-the-marshaling-library-with-a-conversion-that-does-not-require-a-context"></a>コンテキストが不要な変換でマーシャ リング ライブラリを拡張するには  
  
1.  新しいのマーシャ リング関数 MyMarshal.h などを格納するファイルを作成します。  
  
2.  マーシャ リング ライブラリ ファイルの 1 つ以上を含めます。  
  
    -   基本型の marshal.h します。  
  
    -   windows のデータ型の marshal_windows.h します。  
  
    -   C++ 標準ライブラリのデータ型の marshal_cppstd.h します。  
  
    -   ATL のデータ型の marshal_atl.h します。  
  
3.  次の手順の最後にコードを使用して、変換関数を作成します。 型に変換するには、FROM、変換後の型は、このコードでと`from`変換されるパラメーターです。  
  
4.  変換ロジックに関するコメントを変換するコードに置き換えます、 `from` TO のオブジェクトにパラメーターを入力し、変換後のオブジェクトを返します。  
  
```  
namespace msclr {  
   namespace interop {  
      template<>  
      inline TO marshal_as<TO, FROM> (const FROM& from) {  
         // Insert conversion logic here, and return a TO parameter.  
      }  
   }  
}  
```  
  
### <a name="to-extend-the-marshaling-library-with-a-conversion-that-requires-a-context"></a>コンテキストを必要とする変換でマーシャ リング ライブラリを拡張するには  
  
1.  新しいのマーシャ リング関数 MyMarshal.h などを格納するファイルを作成します。  
  
2.  マーシャ リング ライブラリ ファイルの 1 つ以上を含めます。  
  
    -   基本型の marshal.h します。  
  
    -   windows のデータ型の marshal_windows.h します。  
  
    -   C++ 標準ライブラリのデータ型の marshal_cppstd.h します。  
  
    -   ATL のデータ型の marshal_atl.h します。  
  
3.  次の手順の最後にコードを使用して、変換関数を作成します。 型に変換するには、FROM、変換後の型は、このコードで`toObject`、結果を格納するためのポインターと`fromObject`変換されるパラメーターです。  
  
4.  初期化するコードを使用して初期化するに関するコメントを置き換える、`toPtr`適切な空の値にします。 たとえば、ポインターである場合に設定`NULL`です。  
  
5.  変換ロジックに関するコメントを変換するコードに置き換えます、`from`のオブジェクトにパラメーター *TO*型です。 この変換されたオブジェクトは`toPtr`します。  
  
6.  コメントを設定するには、`toObject`を設定するコードと`toObject`変換後のオブジェクトにします。  
  
7.  によって割り当てられたメモリを解放するコードとネイティブ リソースのクリーンアップに関するコメント`toPtr`です。 場合`toPtr`を使用してメモリを割り当てられた`new`を使用して`delete`メモリを解放します。  
  
```  
namespace msclr {  
   namespace interop {  
      template<>  
      ref class context_node<TO, FROM> : public context_node_base  
      {  
      private:  
         TO toPtr;  
      public:  
         context_node(TO& toObject, FROM fromObject)  
         {  
            // (Step 4) Initialize toPtr to the appropriate empty value.  
            // (Step 5) Insert conversion logic here.  
            // (Step 6) Set toObject to the converted parameter.  
         }  
         ~context_node()  
         {  
            this->!context_node();  
         }  
      protected:  
         !context_node()  
         {  
            // (Step 7) Clean up native resources.  
         }  
      };  
   }  
}   
```  
  
## <a name="example"></a>例  
 次の例では、コンテキストが不要な変換でマーシャ リング ライブラリを拡張します。 この例ではコードはネイティブ データ型から、従業員の情報にマネージ データ型に変換します。  
  
```  
// MyMarshalNoContext.cpp  
// compile with: /clr  
#include <msclr/marshal.h>  
  
value struct ManagedEmp {  
   System::String^ name;  
   System::String^ address;  
   int zipCode;  
};  
  
struct NativeEmp {  
   char* name;  
   char* address;  
   int zipCode;  
};  
  
namespace msclr {  
   namespace interop {  
      template<>  
      inline ManagedEmp^ marshal_as<ManagedEmp^, NativeEmp> (const NativeEmp& from) {  
         ManagedEmp^ toValue = gcnew ManagedEmp;  
         toValue->name = marshal_as<System::String^>(from.name);  
         toValue->address = marshal_as<System::String^>(from.address);  
         toValue->zipCode = from.zipCode;  
         return toValue;  
      }  
   }  
}  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {   
   NativeEmp employee;  
  
   employee.name = "Jeff Smith";  
   employee.address = "123 Main Street";  
   employee.zipCode = 98111;  
  
   ManagedEmp^ result = marshal_as<ManagedEmp^>(employee);  
  
   Console::WriteLine("Managed name: {0}", result->name);  
   Console::WriteLine("Managed address: {0}", result->address);  
   Console::WriteLine("Managed zip code: {0}", result->zipCode);  
  
   return 0;  
}  
```  
  
 前の例で、`marshal_as`関数は、変換後のデータにハンドルを返します。 これは、データの追加コピーを作成されないようにするために行われました。 変数を直接返すことがある、不要なパフォーマンス コスト関連付けられています。  
  
```Output  
Managed name: Jeff Smith  
Managed address: 123 Main Street  
Managed zip code: 98111  
```  
  
## <a name="example"></a>例  
 次の例は、従業員情報をマネージ データ型からネイティブ データ型に変換します。 この変換には、マーシャ リング コンテキストが必要です。  
  
```  
// MyMarshalContext.cpp  
// compile with: /clr  
#include <stdlib.h>  
#include <string.h>  
#include <msclr/marshal.h>  
  
value struct ManagedEmp {  
   System::String^ name;  
   System::String^ address;  
   int zipCode;  
};  
  
struct NativeEmp {  
   const char* name;  
   const char* address;  
   int zipCode;  
};  
  
namespace msclr {  
   namespace interop {  
      template<>  
      ref class context_node<NativeEmp*, ManagedEmp^> : public context_node_base  
      {  
      private:  
         NativeEmp* toPtr;  
         marshal_context context;  
      public:  
         context_node(NativeEmp*& toObject, ManagedEmp^ fromObject)  
         {  
            // Conversion logic starts here  
            toPtr = NULL;  
  
            const char* nativeName;  
            const char* nativeAddress;  
  
            // Convert the name from String^ to const char*.  
            System::String^ tempValue = fromObject->name;  
            nativeName = context.marshal_as<const char*>(tempValue);  
  
            // Convert the address from String^ to const char*.  
            tempValue = fromObject->address;  
            nativeAddress = context.marshal_as<const char*>(tempValue);  
  
            toPtr = new NativeEmp();  
            toPtr->name = nativeName;  
            toPtr->address = nativeAddress;  
            toPtr->zipCode = fromObject->zipCode;  
  
            toObject = toPtr;  
         }  
         ~context_node()  
         {  
            this->!context_node();  
         }  
      protected:  
         !context_node()  
         {  
            // When the context is deleted, it will free the memory  
            // allocated for toPtr->name and toPtr->address, so toPtr  
            // is the only memory that needs to be freed.  
            if (toPtr != NULL) {  
               delete toPtr;  
               toPtr = NULL;  
            }  
         }  
      };  
   }  
}   
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   ManagedEmp^ employee = gcnew ManagedEmp();  
  
   employee->name = gcnew String("Jeff Smith");  
   employee->address = gcnew String("123 Main Street");  
   employee->zipCode = 98111;  
  
   marshal_context context;  
   NativeEmp* result = context.marshal_as<NativeEmp*>(employee);  
  
   if (result != NULL) {  
      printf_s("Native name: %s\nNative address: %s\nNative zip code: %d\n",  
         result->name, result->address, result->zipCode);  
   }  
  
   return 0;  
}  
```  
  
```Output  
Native name: Jeff Smith  
Native address: 123 Main Street  
Native zip code: 98111  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ におけるマーシャリングの概要](../dotnet/overview-of-marshaling-in-cpp.md)