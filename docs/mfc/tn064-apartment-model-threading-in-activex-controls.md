---
title: 'TN064: ActiveX コントロールにおけるアパートメント モデルのスレッド化 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.controls.activex
dev_langs:
- C++
helpviewer_keywords:
- OLE controls [MFC], container support
- containers [MFC], multithreaded
- TN064 [MFC]
- multithread container [MFC]
- apartment model threading [MFC]
ms.assetid: b2ab4c88-6954-48e2-9a74-01d4a60df073
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 515103fc66ad221a3806fc101dcbc01f507ef535
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383189"
---
# <a name="tn064-apartment-model-threading-in-activex-controls"></a>テクニカル ノート 64: ActiveX コントロールにおけるアパートメント モデルのスレッド処理
> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 このテクニカル ノートでは、ActiveX コントロールにおけるアパートメント モデルのスレッドを有効にする方法について説明します。 アパートメント モデルのスレッドのみでサポートされている Visual C version 4.2 以降に注意してください。  
  
## <a name="what-is-apartment-model-threading"></a>アパートメント モデルのスレッドとは  
 アパートメント モデルは、マルチ スレッド コンテナー アプリケーション内での ActiveX コントロールなどの埋め込みオブジェクトをサポートする方法です。 アプリケーションには、複数のスレッドがありますが、1 つ"アパートメントに、"1 つのスレッドで実行されますが、埋め込みオブジェクトの各インスタンスが割り当てられます。 つまり、コントロールのインスタンスのすべての呼び出しは、同じスレッドで実行されます。  
  
 ただし、コントロールの同じ型の別のインスタンスは、異なるアパートメント内に割り当てることができます。 そのため、コントロールの複数のインスタンスは、一般的な (たとえば、静的データまたはグローバル データ) 内のデータを共有している場合、この共有データへのアクセスは、クリティカル セクションなどの同期オブジェクトで保護する必要があります。  
  
 アパートメント スレッド モデルの完全な詳細については、「[プロセスとスレッド](http://msdn.microsoft.com/library/windows/desktop/ms684841)で、 *OLE プログラマーズ リファレンス*です。  
  
## <a name="why-support-apartment-model-threading"></a>アパートメント モデルのスレッドをサポートする理由  
 また、アパートメント モデルをサポートするマルチ スレッド コンテナー アプリケーションでは、アパートメント モデルのスレッドをサポートするコントロールを使用できます。 アパートメント モデルのスレッドを有効にしない場合は、コントロールを使用することがコンテナーの潜在的なセットを制限します。  
  
 アパートメント モデルのスレッドの有効化はまったくまたはほとんどの共有データがある場合に特にほとんどのコントロールは簡単です。  
  
## <a name="protecting-shared-data"></a>共有データの保護  
 コントロールは、共有のデータを使用している場合など、静的メンバー変数へのアクセスを複数のスレッドが同時にデータを変更することを防ぐために、クリティカル セクションのデータを保護する必要があります。 この目的のため、クリティカル セクションをセットアップするクラスの静的メンバー変数を宣言`CCriticalSection`コントロールのクラスでします。 使用して、`Lock`と**Unlock**このクリティカル セクションのメンバー関数は、コード共有のデータにアクセスするオブジェクトします。  
  
 たとえば、すべてのインスタンスによって共有されている文字列を管理する必要があるコントロール クラスを検討します。 この文字列は、静的メンバー変数に保持されるあり、クリティカル セクションによって保護されていることができます。 コントロールのクラス宣言には、次が含まれます。  
  
```  
class CSampleCtrl : public COleControl  
{  
 ...  
    static CString _strShared;  
    static CCriticalSection _critSect;  
};  
```  
  
 このクラスの実装には、これらの変数の定義が含まれます。  
  
```  
int CString CSampleCtrl::_strShared;  
CCriticalSection CSampleCtrl::_critSect;  
```  
  
 アクセス、`_strShared`静的メンバーは、クリティカル セクションによって保護されます。  
  
```  
void CSampleCtrl::SomeMethod()  
{  
    _critSect.Lock();
if (_strShared.Empty())  
    _strShared = "<text>";  
    _critSect.Unlock();

 ...  
}  
```  
  
## <a name="registering-an-apartment-model-aware-control"></a>アパートメント モデル対応コントロールの登録  
 アパートメント モデルのスレッドをサポートするコントロールは、クラス ID レジストリ エントリの下で「アパートメント」の値を持つ"ThreadingModel"の名前付きの値を追加することによってレジストリで、この機能を指定する必要があります、*クラス id* \\ **InprocServer32**キー。 コントロールに自動的に登録するには、このキーには、渡す、 `afxRegApartmentThreading` 6 番目のパラメーターでフラグ`AfxOleRegisterControlClass`:  
  
```  
BOOL CSampleCtrl::CSampleCtrlFactory::UpdateRegistry(BOOL bRegister)  
{  
    if (bRegister)  
    return AfxOleRegisterControlClass(
    AfxGetInstanceHandle(), 
    m_clsid, 
    m_lpszProgID, 
    IDS_SAMPLE, 
    IDB_SAMPLE, 
    afxRegApartmentThreading, 
    _dwSampleOleMisc, 
    _tlid, 
    _wVerMajor, 
    _wVerMinor);

 else  
    return AfxOleUnregisterClass(m_clsid,
    m_lpszProgID);

}  
```  
  
 コントロール プロジェクトは、ControlWizard 4.1 またはそれ以降のバージョンの Visual c で生成された場合、このフラグは、コードで存在でしょう。 変更する、スレッディング モデルを登録する必要はありません。  
  
 プロジェクトは、以前のバージョンの ControlWizard によって生成された、既存のコードは、6 番目のパラメーターとしてブール値があります。 既存のパラメーターが TRUE の場合に変更`afxRegInsertable | afxRegApartmentThreading`です。 既存のパラメーターが FALSE の場合に変更`afxRegApartmentThreading`です。  
  
 コントロールがアパートメント モデルのスレッドの規則を遵守しない場合で渡さないでください`afxRegApartmentThreading`このパラメーターにします。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

