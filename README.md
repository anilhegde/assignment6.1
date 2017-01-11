ackage session6;

import java.util.concurrent.Executors;
import java.util.concurrent.ScheduledExecutorService;
import java.util.concurrent.TimeUnit;

public class Assignment61 {

	public static void main(String[] args) throws InterruptedException {
		Runnable r = new Updater();
		ScheduledExecutorService service = Executors.newScheduledThreadPool(1);
		service.scheduleAtFixedRate(r, 0, 3, TimeUnit.SECONDS);
		
		Thread.sleep(30000);//so that it prints 11 times
        service.shutdown();
	}

}

class Updater implements Runnable {

	@Override
	public void run() {
		System.out.println("3 second passed");

	}

}
