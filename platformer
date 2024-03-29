import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.KeyEvent;
import java.awt.event.KeyListener;
import java.util.ArrayList;
import java.util.List;
import java.util.Random;

public class PlatformerGame extends JPanel implements ActionListener, KeyListener {
    private int playerX, playerY;
    private boolean isJumping;
    private List<Enemy> enemies; 
    private List<Platform> platforms; 
    private int currentLevel; 
    private Timer timer;

    public PlatformerGame() {
        
        playerX = 100;
        playerY = 400;
        isJumping = false;

        
        enemies = new ArrayList<>();
        platforms = new ArrayList<>();
        spawnEnemies();
        spawnPlatforms();

        
        timer = new Timer(16, this);
        timer.start();

        
        addKeyListener(this);
        setFocusable(true);
    }

    

    public void paintComponent(Graphics g) {
        super.paintComponent(g);

        
        g.setColor(new Color(135, 206, 235)); // Sky blue color
        g.fillRect(0, 0, getWidth(), getHeight());

        
        g.setColor(Color.GREEN);
        for (Platform platform : platforms) {
            g.fillRect(platform.getX(), platform.getY(), platform.getWidth(), platform.getHeight());
        }

        
        g.setColor(Color.BLUE);
        g.fillRect(playerX, playerY, 30, 30);

        
        g.setColor(Color.RED);
        for (Enemy enemy : enemies) {
            g.fillRect(enemy.getX(), enemy.getY(), 20, 20);
        }
    }

    
}
