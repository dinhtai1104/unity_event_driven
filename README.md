# unity_event_driven
## How to use?
```csharp
public class UIMain : MonoBehaviour 
{
      [SerializeField] private UIWin uiWin;
      void OnEnable() 
      {
          Messenger.AddListener(EventKey.WINGAME, OnWinGame);
      }
      void OnDisable() 
      {
          Messenger.RemoveListener(EventKey.WINGAME, OnWinGame); // Always remember to remove this listener
      }
      
      private void OnWinGame() 
      {
          uiWin.Show();
      }
}

public class GameController : MonoBehaviour 
{
      void WinGame() 
      {
          Messenger.Broadcast(EventKey.WINGAME);
      }
}

```
