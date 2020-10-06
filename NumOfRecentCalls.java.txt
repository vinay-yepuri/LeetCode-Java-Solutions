
class RecentCounter {
    
    private List<Integer> pingList = new ArrayList<>();
    
    
    private final int RANGE_CONSTANT = 3000;

    public RecentCounter() {
    }
    
    public int ping(int t) {
        
        int minRange = t-RANGE_CONSTANT;
        pingList.add(t);
        
		// pingList.removeIf(pingItem -> pingItem < minRange);
        Iterator<Integer> pingItr = pingList.iterator();
        
        while(pingItr.hasNext()){
            
            if(pingItr.next() < minRange)
                pingItr.remove();
        }
        
        return ( pingList.size() == 0)? null : pingList.size();
    }
}

/**
 * Your RecentCounter object will be instantiated and called as such:
 * RecentCounter obj = new RecentCounter();
 * int param_1 = obj.ping(t);
 */