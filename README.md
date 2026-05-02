# EventBus
> Unity Struct-Based Global Event System

- Decoupled
- Safe Invocation

- no Boxing (Struct 제약)
- no Garbage 

## 이벤트 정의
```csharp
public struct OnPlayerDashed { public int continusCount; public DashInfo info; }
public struct OnPlayerGrabbed { public TargetInfo target; }
public struct OnCoinsChanged { public int before; public int after; public int changeAmount; }
```

## 기능
- **Publish / Subscribe / Unsubscribe** : 전역 이벤트 발행, 구독, 해제
- Safe Invocation
- Shortcut ( Pub / Sub / Unsub )

## Example
```csharp
EventBus.Pub(new OnPlayerDashed { continusCount = 1, info = dashInfo });
EventBus.Sub<OnPlayerDashed>(OnDash);
```
